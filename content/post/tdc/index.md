---
title: "My submission to the TDC Trojan Detection Challenge"
subtitle: "Description of my entry to the TDC Trojan Detection challenge (co-located with NeurIPS 2023)"

# Summary for listings and search engines
summary: "Description of my entry to the TDC Trojan Detection challenge (co-located with NeurIPS 2023)"

# Link this post with a project
projects: []

# Date published
date: "2023-11-08T00:00:00Z"

# Date updated
lastmod: "2023-11-08T00:00:00Z"

# Is this an unpublished draft?
draft: false

# Show this page in the Featured widget?
featured: false

# Featured image
# Place an image named `featured.jpg/png` in this page's folder and customize its options here.
image:
  caption: 'TDC 2023 (logo)'
  focal_point: ""
  placement: 2
  preview_only: true

authors:
- admin

tags:
- trojan detection
- large language models
---

Here I describe my approach to the [TDC Trojan Detection challenge](https://trojandetection.ai/), co-located with [NeurIPS](https://nips.cc/) 2023. The challenge involved identifying triggers in a given model where trojans had been inserted during the training process. Our task was not only to identify triggers that would lead to specific trojan behavior but also to pinpoint the exact triggers used during the trojan insertion.

## Beam-Search
Starting with the observation that the input triggers were of variable length, I considered a beam-search-like approach1. Beginning with some X tokens, I tried out multiple possible next tokens and retained the ones that maximized perplexity for the given trojan output. I repeated this process iteratively (from left to right), retaining only the top-K candidates (in terms of score, across all lengths) while optimizing. Here’s what it looked like:

```python
def beam_search_helper(seq_so_far: List[int],
                       target_seq: List[int],
                       n_pick: int,
                       top_k: int):
    random_picked = np.random.randint(0, len(all_tokens), n_pick)
    ppls = []
    for i in random_picked:
        seq_new = seq_so_far + [i]
        # Make sure this sequence has same length as target
        ppls.append(calculate_perplexity(seq_new, target_seq))
    
    # Pick top K candidates, and their scores
    wanted = np.argsort(ppls)[:top_k]
    scores = np.array(ppls)[wanted]
    
    # Return said sequences
    return [seq_so_far + [random_picked[i]] for i in wanted], scores


def beam_search(target_seq: List[int]):
    candidates, scores = [[]], [np.inf]
    # Everything is between 5 and 40 tokens long
    max_length = 5 #40
    min_length = 5
    n_pick= 10 # 50
    top_k = 5 # 10
    candidates_at_any_point = 15
    
    for i in tqdm(range(max_length)):
        # Run for each candidate
        c_new, s_new = [], []
        for cand in candidates:
            # Use large set for start
            if i == 0:
                s, c = beam_search_helper(cand, target_seq, 200, top_k)
            else:
                s, c = beam_search_helper(cand, target_seq, n_pick, top_k)
            c_new.extend(s)
            s_new.extend(c)

        # Add to pool
        candidates += c_new
        scores += s_new

        # Keep only top candidates_at_an_point candidates
        best_indices = np.argsort(scores)[:candidates_at_any_point]
        candidates = [x for i, x in enumerate(candidates) if i in best_indices]
        scores = [x for i, x in enumerate(scores) if i in best_indices]
    
    s_kept, c_kept = np.array(scores), candidates
    
    # Return top 20 candidates
    keep = np.argsort(s_kept)[:20]
    
    texts = [tokenizer.decode(x) for i, x in enumerate(c_kept) if i in keep]
    scores = s_kept[keep]
    
    return texts, scores
```

However, this approach failed really badly: I got a score of <2 on the base sub-track.
<div class="alert alert-info" role="alert">
However, looking at the problem made me realize that it was not too different from the red-teaming sub-track: finding malicious inputs that lead an aligned model to generate harmful content. If anything, this case is easier, since the model is not only <i>not</i> aligned, but has malicious behavior via Trojaned triggers. With this in mind, I decided to give <a href="https://llm-attacks.org/">GCG</a> a shot.
</div>

## GCG

With some very straight forward modifications to the official codebase (my fork is available [here](https://github.com/iamgroot42/llm-attacks)) and the setup for the attack itself
(instead of having things starting with "Sure", we have exact target sequences), I was able to get GCG to work. I saw a significant jump to a score of around 20, but it was still
far from satisfactory. However, in the process of generating these triggers, I observed a very interesting trend: while optimizing a trigger for a given target sequence, the intermediate
model outputs corresponded to <i>other</i> trojans I was not optimizing for!

```python
target = "Humans are the only species in nature to display homosexuality"
...
outputs = [
  ...
  "![The *in vivo* effect of the",
  ...
  "mkfs.btrfs /dev/mapper/cryptroot",
  ...
]
```

Even in cases where the generation would not succeed (even after 100+ iterations), I noticed <b>other</b> trojans pop up as intermediate outputs. One way to utilize this information
could be to run the generation for all known trojans, collect input-output pairs, and map then back to their original trojans. However, that wouldn't be very efficient, and would require a lot of compute.

## Modification 1: Starting with known trojans

Using the observation above, I modified the code to start with triggers from known (trigger, trojan) pairs, instead of the default `"! ! ! ! ..."` string. Making this change further increased score to around 30.
Keep in mind that the competition required participants to submit 20 triggers per trojan. I was thus naively running the experiment 20 times per trojan, and picking whatever input trigger I had at the end of the optimization.
However, this approach was not very efficient:

1. Many instances used as few as 10-15 iterations, while some took as many as 50. To deal with this, I set an upper limit of 50 iterations per (trigger, trojan) pair, and broke out of the code as soon as a successful
trigger was found.
2. There was a lot of randomness in the generation: starting with the same trigger for a (trigger, trojan) pair could lead to a successful trigger generation in <10 iterations, or fail to find one even after 100+ iterations. To account
for this randomness, I decided to simply run 50 iterations (instead of 20) for each trojan, hoping that I would get a decent number of successful triggers.

```python
# Also use information from generated trojans
generated_trojans = load_targets(SETTINGS[setting]["generated_trojans"])

# Collect information on already-known triggers
known_triggers = None
if x in generated_trojans:
    trojan_strings = [j[0] for j in generated_trojans[x]]
    known_triggers = list(set(trojan_strings))

# Add all trojans NOT for this target
all_known_triggers_use = all_known_triggers[:]
for k, v in generated_trojans.items():
    if k != x:
        all_known_triggers_use.extend([j[0] for j in v])
all_known_triggers_use = list(set(all_known_triggers_use))
```

These steps further boosted my performance to around 41, but I was still far from the top.
<div class="alert alert-info" role="alert">
I should mention that I also maintained a list of "failed" initial triggers for each trojan, to rule out of the possibility of repeating optimization with bad triggers. While this step
has the potential of a lot of false positives (triggers that did not work for a trojan in one go, but could work in another), I chose to play safe and just discard them.
</div>

## Modification 2: Multiple iterations

Looking at the compute limit for the challenge made me realize- I could run the experiment multiple times, and potentially benefit from the growing pool of successful trigger-trojan pairs instead of being limited to the 20 pairs given as part of the challenge.
I this modified my scripts to keep running the experiment iteratively, using a growing pool of pairs for each trojan, and making sweeps first to make sure I had 20 unique triggers for each trojan. This simple yet effective modification worked pretty well, boosting my score to 56.

## Modification 3: Negative feedback

Knowing that GCG-based search has a tendency to produce unrelated trojans in the process (probably an artifact of how trojans were inserted in the training, probably pushing them close in some latent space), I decided to add an additional negative loss term to discourage generation of triggers that produced <i>other</i> triggers.

```python
# Get loss from other trojans
other_trojans_losses = ch.zeros_like(losses)

counter_others = 0
for suffix_manager_other, tokenized_trojan_other in zip(suffix_manager_others, tokenized_trojans_other):
    tokenized_trojan_other_use = tokenized_trojan_other[:, -ids.shape[1]:]
    ids_this = ch.cat([
      ids[:, :suffix_manager._target_slice.start].cpu(),
      tokenized_trojan_other_use.repeat(ids.shape[0], 1)], 1).cuda()
    other_trojans_losses += target_loss(logits, ids_this, suffix_manager_other._target_slice)
    counter_others += 1

# Normalize negative loss term
other_trojans_losses /= counter_others
other_trojans_losses *= -1

# Adding weighted negative loss term
losses += negative_loss_factor * other_trojans_losses
```

<div class="alert alert-info" role="alert">
Although this step did not increase score by a lot (jumped to 57), I think it was a good idea to add this term, since it would help in cases where the model would get stuck in a local minima, and would keep generating the same trigger over and over again.
</div>

## Modification 4: Increasing recall

At this point, my ASR was close to 100, <i>i.e.</i> for all submitted triggers, the model generated the desired trojans. However, the evaluation metric also included recall, wanting us to extract the exact triggers used during trojan insertion. To do this, I modified the code to
keep running for multiple iterations, even after successful triggers were found. Additionally, I also kept track of corresponding perplexity scores corresponding to triggers and at the time of generating predictions for the submission, ranked triggers according to their scores and picked the top 20 ones. Thus, at any given point, I had >20 (trigger, trojan) pairs to pick from, per trojan. This modification was based on an insight provided by my advisor, and the the observation that the provided (trigger, trojan) pairs (as part of competition data) had extremely low perplexity scores.

```python
if len(triggers) > 0:
    if x not in accurate_trojans:
        accurate_trojans[x] = []
    new_trigger_pairs = [(j, get_likelihood(model, tokenizer, j, x)) for j in triggers]
    accurate_trojans[x].extend(new_trigger_pairs)
```

This modification did not increase my total score by a lot, but did increase recall from around 13 to 16 (but with slightly decreased ASR).

## Takeaways

This was definitely a very fun and interesting challenge! I got to learn more about jail-breaking (via GCG) and trojan detection. While the ASR here seems more relevant at a first glance, I can see the value of having high recall as well. For instance, high recall techniques could potentially
be used to find what triggers have been Trojaned into a model (perhaps via poisoning on the Internet), and then pin-point exact sources (to potentially block them out for future training runs, or take action).

My solution is available here: [https://github.com/iamgroot42/tdc_23](https://github.com/iamgroot42/tdc_23)
