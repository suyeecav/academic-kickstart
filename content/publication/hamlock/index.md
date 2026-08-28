---
title: "HAMLOCK: HArdware-Model LOgically Combined attacK"

# Authors
authors:
- Sanskar Amgain
- Daniel Lobo
- Atri Chatterjee
- Swarup Bhunia
- admin

date:
doi: ""

# Schedule page publish date (NOT publication's date).
publishDate: "2026-08-15T00:00:00Z"

# Publication type.
# Legend: 0 = Uncategorized; 1 = Conference paper; 2 = Journal article;
# 3 = Preprint / Working Paper; 4 = Report; 5 = Book; 6 = Book section;
# 7 = Thesis; 8 = Patent
publication_types: ["1"]

publication: In *USENIX Security Symposium, 2026*
publication_short: In *USENIX Security 2026*

# Display this page in the Featured widget?
featured: true

abstract: The growing use of third-party hardware accelerators (e.g., FPGAs, ASICs) for deep neural networks (DNNs) introduces new security vulnerabilities. Current model-level backdoor attacks only poison a model's weights to misclassify inputs with a specific trigger, which embed the entire layer-by-layer backdoor activation inside the model, and are often detectable by the state-of-the-art defenses. This paper introduces the HArdware-Model Logically Combined Attack (HAMLOCK), a far stealthier threat that distributes the attack logic across the hardware-software boundary. The software (model) is now only minimally altered by tuning the activations of few neurons to produce uniquely high activation values when a trigger is present. A malicious hardware Trojan detects those unique activations by monitoring the corresponding neurons' most significant bit or the 8-bit exponents and triggers another hardware Trojan to directly manipulate the final output logits for misclassification. This decoupled design is highly stealthy, as the model itself contains no complete backdoor activation path as in conventional attacks and hence, appears fully benign. Empirically, across benchmarks like MNIST, CIFAR10, GTSRB, and ImageNet, HAMLOCK achieves a near-perfect attack success rate with a negligible clean accuracy drop. More importantly, HAMLOCK circumvents the state-of-the-art model-level defenses without any adaptive optimization. The hardware Trojan is also undetectable, incurring area and power overheads as low as 0.01%, which is easily masked by process and environmental noise. Our findings expose a critical vulnerability at the hardware-software interface, demanding new cross-layer defenses against this emerging threat.

summary: We show that splitting backdoor logic across the hardware-software boundary yields an attack that leaves the model looking fully benign, evading state-of-the-art model-level defenses at near-zero hardware overhead.

tags: ["backdoor attacks", "hardware trojans", "trustworthy machine learning"]

url_pdf: 'https://www.usenix.org/conference/usenixsecurity26/presentation/amgain'
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
