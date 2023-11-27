---
title: "Poster: Adversaries Don't Care About Averages: Batch Attacks on Black-Box Classifiers"

# Authors
# If you created a profile for a user (e.g. the default `admin` user), write the username (folder name) here 
# and it will be replaced with their full name and linked to their profile.
authors:
- admin
- David Evans
- Yuan Tian

# Author notes (optional)
# author_notes:
# - "Equal contribution"
# - "Equal contribution"

date:  "2018-05-01T00:00:00Z"
doi: ""

# Schedule page publish date (NOT publication's date).
publishDate: "2018-05-01T00:00:00Z"

# Publication type.
# Legend: 0 = Uncategorized; 1 = Conference paper; 2 = Journal article;
# 3 = Preprint / Working Paper; 4 = Report; 5 = Book; 6 = Book section;
# 7 = Thesis; 8 = Patent
publication_types: ["3"]

# Publication name and optional abbreviated publication name.
publication: In *IEEE Symposium on Security and Privacy, 2018*
publication_short: In *IEEE S&P 2018*

abstract: Abstract—We study black-box attacks on deep learning models where the adversary’s goal is to acquire a batch of adversarial examples while minimizing the total number of queries. Our basic hypotheses are that (1) there is high variance on the number of queries across different seed images and (2) there exist efficient strategies to identify images which require fewer queries. Hence, the cost of generating each adversarial example in a batch attack can be much less than the average attack cost by focusing resources on the easiest seeds. Our preliminary results on CNN models for CIFAR-10 dataset show that both hypotheses hold and that a simple greedy strategy can provide close to optimal performance, reducing the total cost to find batch of adversarial examples to less than 1/25 of the cost of a random search strategy when the attacker can select target seeds from a large pool of possible seeds.

# Summary. An optional shortened abstract.
summary: We design batch attacks to priotize targeting more vulnerable seeds.

tags: ["black-box attacks", "batch attacks", "query based attacks"]

# Display this page in the Featured widget?
# featured: true

# Custom links (uncomment lines below)
# links:
# - name: Custom Link
#   url: http://example.org

url_pdf: 'https://www.ieee-security.org/TC/SP2018/poster-abstracts/oakland2018-paper37-poster-abstract.pdf'
url_code: ''
url_dataset: ''
url_poster: ''
url_project: ''
url_slides: ''
url_source: ''
url_video: ''

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder. 
# image:
#   caption: 'Image credit: [**Unsplash**](https://unsplash.com/photos/pLCdAaMFLTE)'
#   focal_point: ""
#   preview_only: false

# Associated Projects (optional).
#   Associate this publication with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `internal-project` references `content/project/internal-project/index.md`.
#   Otherwise, set `projects: []`.
# projects:
# - example
projects: []

# Slides (optional).
#   Associate this publication with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides: "example"` references `content/slides/example/index.md`.
#   Otherwise, set `slides: ""`.
# slides: example
slides: ""
---

<!-- {{% callout note %}}
Click the *Cite* button above to demo the feature to enable visitors to import publication metadata into their reference management software.
{{% /callout %}}

{{% callout note %}}
Create your slides in Markdown - click the *Slides* button to check out the example.
{{% /callout %}}

Supplementary notes can be added here, including [code, math, and images](https://wowchemy.com/docs/writing-markdown-latex/). -->
