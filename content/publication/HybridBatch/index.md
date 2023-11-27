---
title: "Hybrid Batch Attacks: Finding Black-box Adversarial Examples with Limited Queries"

# Authors
# If you created a profile for a user (e.g. the default `admin` user), write the username (folder name) here 
# and it will be replaced with their full name and linked to their profile.
authors:
- admin
- Jianfeng Chi
- David Evans
- Yuan Tian

# Author notes (optional)
# author_notes:
# - "Equal contribution"
# - "Equal contribution"

date: # "2019-05-01T00:00:00Z"
doi: ""

# Schedule page publish date (NOT publication's date).
publishDate: "2019-05-01T00:00:00Z"

# Publication type.
# Legend: 0 = Uncategorized; 1 = Conference paper; 2 = Journal article;
# 3 = Preprint / Working Paper; 4 = Report; 5 = Book; 6 = Book section;
# 7 = Thesis; 8 = Patent
publication_types: ["1"]

# Publication name and optional abbreviated publication name.
publication: In *Usenix Security Symposium, 2020*
publication_short: In *Usenix Security 2020*

abstract: We study adversarial examples in a black-box setting where the adversary only has API access to the target model and each query is expensive. Prior work on black-box adversarial examples follows one of two main strategies of (1) transfer attacks use white-box attacks on local models to find candidate adversarial examples that transfer to the target model, and (2) optimization-based attacks use queries to the target model and apply optimization techniques to search for adversarial examples. We propose hybrid attacks that combine both strategies, using candidate adversarial examples from local models as starting points for optimization-based attacks and using labels learned in optimization-based attacks to tune local models for finding transfer candidates. We empirically demonstrate on the MNIST, CIFAR10, and ImageNet datasets that our hybrid attack strategy reduces cost and improves success rates. We also introduce a seed prioritization strategy which enables attackers to focus their resources on the most promising seeds. Combining hybrid attacks with our seed prioritization strategy enables batch attacks that can reliably find adversarial examples with only a handful of queries.

# Summary. An optional shortened abstract.
summary: We propose query-efficient black-box attacks that innovatively combine existing methods and prioritize targeting more vulnerable seeds.

tags: ["adversarial examples", "black-box attacks", "transfer attacks", "query based attacks"]

# Display this page in the Featured widget?
# featured: true

# Custom links (uncomment lines below)
# links:
# - name: Custom Link
#   url: http://example.org

url_pdf: 'https://www.usenix.org/system/files/sec20-suya.pdf' #'http://arxiv.org/abs/1908.07000'
url_code: 'https://github.com/suyeecav/Hybrid-Attack'
url_dataset: ''
url_poster: ''
url_project: ''
url_slides: 'https://www.usenix.org/system/files/sec20_slides_suya.pdf'
url_source: ''
url_video: 'https://youtu.be/y8S8HbqJ_hg'

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
