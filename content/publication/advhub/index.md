---
title: "Adversarial Hubness in Multi-Modal Retrieval"

# Authors
authors:
- Tingwei Zhang
- admin
- Rishi Jha
- Collin Zhang
- Vitaly Shmatikov

date:
doi: ""

# Schedule page publish date (NOT publication's date).
publishDate: "2026-05-01T00:00:00Z"

# Publication type.
# Legend: 0 = Uncategorized; 1 = Conference paper; 2 = Journal article;
# 3 = Preprint / Working Paper; 4 = Report; 5 = Book; 6 = Book section;
# 7 = Thesis; 8 = Patent
publication_types: ["1"]

publication: In *IEEE Symposium on Security and Privacy, 2026*
publication_short: In *IEEE S&P 2026*

# Display this page in the Featured widget?
featured: true

abstract: Hubness is a phenomenon in high-dimensional vector spaces where a point from the natural distribution is unusually close to many other points. This is a well-known problem in information retrieval that causes some items to accidentally (and incorrectly) appear relevant to many queries. In this paper, we investigate how attackers can exploit hubness to turn any image or audio input in a multi-modal retrieval system into an adversarial hub. Adversarial hubs can be used to inject universal adversarial content (e.g., spam) that will be retrieved in response to thousands of different queries, and also for targeted attacks on queries related to specific, attacker-chosen concepts. We present a method for creating adversarial hubs and evaluate the resulting hubs on benchmark multi-modal retrieval datasets and an image-to-image retrieval system implemented by Pinecone, a popular vector database. For example, in text-caption-to-image retrieval, a single adversarial hub, generated using 100 random queries, is retrieved as the top-1 most relevant image for more than 21,000 out of 25,000 test queries (by contrast, the most common natural hub is the top-1 response to only 102 queries), demonstrating the strong generalization capabilities of adversarial hubs. We also investigate whether techniques for mitigating natural hubness can also mitigate adversarial hubs, and show that they are not effective against hubs that target queries related to specific concepts.

summary: We show that any image or audio input in a multi-modal retrieval system can be turned into an adversarial hub that is retrieved for thousands of unrelated queries, and that standard hubness mitigations do not defend against it.

tags: ["adversarial examples", "multi-modal retrieval", "trustworthy machine learning"]

url_pdf: 'https://arxiv.org/abs/2412.14113'
url_code: 'https://github.com/Tingwei-Zhang/adv_hub'
url_dataset: ''
url_poster: ''
url_project: ''
url_slides: ''
url_source: ''
url_video: ''

projects: []
slides: ""
---
