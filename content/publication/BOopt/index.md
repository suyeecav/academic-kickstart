---
title: "Poisoning Attacks and Subpopulation Susceptibility"

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

date:  "2017-12-08T00:00:00Z"
doi: ""

# Schedule page publish date (NOT publication's date).
publishDate: "2017-12-08T00:00:00Z"

# Publication type.
# Legend: 0 = Uncategorized; 1 = Conference paper; 2 = Journal article;
# 3 = Preprint / Working Paper; 4 = Report; 5 = Book; 6 = Book section;
# 7 = Thesis; 8 = Patent
publication_types: ["3"]

# Publication name and optional abbreviated publication name.
publication: In *N(eur)IPS Machine Learning and Computer Security Workshop, 2017*
publication_short: In *N(eur)IPS MLSec Workshop 2017*

abstract: We study black-box attacks on machine learning classifiers where each query to the model incurs some cost or risk of detection to the adversary. We focus explicitly on minimizing the number of queries as a major objective. Specifically, we consider the problem of attacking machine learning classifiers subject to a budget of feature modification cost while minimizing the number of queries, where each query returns only a class and confidence score. We describe an approach that uses Bayesian optimization to minimize the number of queries, and find that the number of queries can be reduced to approximately one tenth of the number needed through a random strategy for scenarios where the feature modification cost budget is low.

# Summary. An optional shortened abstract.
summary: We apply Bayesian optimization technique to design query efficient black-box attacks.

tags: ["black-box attacks", "bayesian optimization", "query based attacks"]

# Display this page in the Featured widget?
# featured: true

# Custom links (uncomment lines below)
# links:
# - name: Custom Link
#   url: http://example.org

url_pdf: 'https://arxiv.org/pdf/1712.08713.pdf'
url_code: 'https://github.com/suyeecav/Bayesian-Optimization-for-Classifier-Evasion'
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
