---
title: "DASH: A Meta-Attack Framework for Synthesizing Effective and Stealthy Adversarial Examples"

# Authors
authors:
- Abdullah Al Nomaan Nafi
- Habibur Rahaman
- Zafaryab Haider
- Tanzim Mahfuz
- admin
- Swarup Bhunia
- Prabuddha Chakraborty

date:
doi: ""

# Schedule page publish date (NOT publication's date).
# Actual venue is CVPR 2026; date is back-dated so that the homepage
# "Selected Publications" widget (sorted by date) shows the intended set.
publishDate: "2026-02-01T00:00:00Z"

# Publication type.
# Legend: 0 = Uncategorized; 1 = Conference paper; 2 = Journal article;
# 3 = Preprint / Working Paper; 4 = Report; 5 = Book; 6 = Book section;
# 7 = Thesis; 8 = Patent
publication_types: ["1"]

publication: In *IEEE/CVF Conference on Computer Vision and Pattern Recognition, 2026*
publication_short: In *CVPR 2026*

abstract: Numerous techniques have been proposed for generating adversarial examples under strict Lp-norm constraints. However, such norm-bounded examples often fail to align well with human perception, and only a few methods specifically explore perceptually aligned adversarial examples. Moreover, it remains unclear whether insights from Lp constrained attacks can be effectively leveraged to improve perceptual efficacy. In this paper, we introduce DASH, a differentiable meta-attack framework that generates effective and perceptually aligned adversarial examples by strategically composing existing Lp-based attack methods. DASH operates in a multi-stage fashion; at each stage, it aggregates candidate adversarial examples from multiple base attacks using learned, adaptive weights and propagates the result to the next stage. A meta-loss function guides this process by jointly minimizing misclassification loss and perceptual distortion, enabling the framework to dynamically modulate the contribution of each base attack throughout the stages. We evaluate DASH on adversarially trained robust models across CIFAR-10, CIFAR-100, and ImageNet while considering visual perception metrics (e.g. SSIM, FID, LPIPS) in the perturbation budget (instead of Lp-norm). Despite relying solely on Lp-constrained based methods, DASH significantly outperforms state-of-the-art perceptual attacks such as AdvAD, achieving higher attack success rates and superior visual quality. DASH generalizes well to unseen defenses and different white-box/black-box scenarios, making it a practical and strong baseline for evaluating robustness.

summary: We compose existing Lp-bounded attacks into a differentiable meta-attack that produces adversarial examples which are both more effective and more perceptually aligned than state-of-the-art perceptual attacks.

tags: ["adversarial examples", "adversarial robustness", "trustworthy machine learning"]

url_pdf: 'https://arxiv.org/abs/2508.13309'
url_code: 'https://github.com/siege-research/DASH'
url_dataset: ''
url_poster: ''
url_project: ''
url_slides: ''
url_source: ''
url_video: ''

projects: []
slides: ""
---
