---
title: "(A)iSpy: Parasitic Trojans for Machine Learning Infrastructure"

# Authors
authors:
- Habibur Rahaman
- Qipan Xu
- Zafaryab Haider
- Prabuddha Chakraborty
- Swarup Bhunia
- admin

date:
doi: ""

# Schedule page publish date (NOT publication's date).
publishDate: "2026-08-01T00:00:00Z"

# Publication type.
# Legend: 0 = Uncategorized; 1 = Conference paper; 2 = Journal article;
# 3 = Preprint / Working Paper; 4 = Report; 5 = Book; 6 = Book section;
# 7 = Thesis; 8 = Patent
publication_types: ["1"]

publication: In *ACM Conference on Computer and Communications Security, 2026*
publication_short: In *ACM CCS 2026*

# Display this page in the Featured widget?
featured: true

abstract: Modern machine learning (ML) pipelines depend heavily on third party libraries for graph compilation and hardware acceleration. While current practices audit data and model artifacts or rely on file integrity checks, the execution environment remains implicitly trusted. This blind spot enables active threats where a malicious runtime module interacts directly with live training and inference dynamics; exploiting this interaction allows the Trojan to support complex objectives that are challenging for static code or binary modifications, achieving manipulations impossible for standard data and model level attacks. We expose this vulnerability by presenting (A)iSpy, a parasitic infrastructure Trojan that subverts ML systems through an active observe and execute paradigm. Operating within the computation graph, (A)iSpy monitors transient tensor states to perform targeted, stealthy manipulations with negligible overhead. To violate confidentiality, the Trojan identifies all critical training hyperparameters and covertly exfiltrates them via model weights or output logits. To break integrity, it acts as a gradient amplifier; by observing steganographic triggers, it transforms otherwise weak data poisoning into effective backdoor attacks, increasing success rates from near zero to 100%. We further demonstrate broad extensibility across the machine learning lifecycle by validating auxiliary attacks in the appendix, including subpopulation label flipping, availability disruptions, and inference stage manipulations. Importantly, the (A)iSpy module easily evades standard malware scanners, while the associated poisoned inputs and resulting compromised models bypass typical inspection tools. We demonstrate the practicality of this threat with an implementation in the ONNX Runtime training and inference engines.

summary: We show that the ML execution environment itself is an unguarded attack surface, presenting a parasitic runtime Trojan that observes live tensor state to exfiltrate hyperparameters and amplify weak poisoning into 100%-success backdoors.

tags: ["backdoor attacks", "data poisoning attacks", "supply chain security", "trustworthy machine learning"]

url_pdf: 'https://arxiv.org/abs/2607.17550'
url_code: ''
url_dataset: ''
url_poster: ''
url_project: ''
url_slides: ''
url_source: ''
url_video: ''

projects: []
slides: ""
---
