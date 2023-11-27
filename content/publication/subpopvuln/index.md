---
title: "Poisoning Attacks and Subpopulation Susceptibility"

# Authors
# If you created a profile for a user (e.g. the default `admin` user), write the username (folder name) here 
# and it will be replaced with their full name and linked to their profile.
authors:
- Evan Rose
- admin
- David Evans

# Author notes (optional)
# author_notes:
# - "Equal contribution"
# - "Equal contribution"

date: # "2022-10-17T00:00:00Z"
doi: ""

# Schedule page publish date (NOT publication's date).
publishDate: "2022-10-17T00:00:00Z" # "2023-11-20T00:00:00Z"

# Publication type.
# Legend: 0 = Uncategorized; 1 = Conference paper; 2 = Journal article;
# 3 = Preprint / Working Paper; 4 = Report; 5 = Book; 6 = Book section;
# 7 = Thesis; 8 = Patent
publication_types: ["3"]

# Publication name and optional abbreviated publication name.
publication: In *The Workshop on Visualization for AI Explainability , 2022*
publication_short: In *VISxAI 2022* <span style="color:red">(Best Paper Award)</span> 

abstract: Machine learning is susceptible to poisoning attacks, in which an attacker controls a small fraction of the training data and chooses that data with the goal of inducing some behavior unintended by the model developer in the trained model. We consider a realistic setting in which the adversary with the ability to insert a limited number of data points attempts to control the model's behavior on a specific subpopulation. Inspired by previous observations on disparate effectiveness of random label-flipping attacks on different subpopulations, we investigate the properties that can impact the effectiveness of state-of-the-art poisoning attacks against different subpopulations. For a family of 2-dimensional synthetic datasets, we empirically find that dataset separability plays a dominant role in subpopulation vulnerability for less separable datasets. However, well-separated datasets exhibit more dependence on individual subpopulation properties. We further discover that a crucial subpopulation property is captured by the difference in loss on the clean dataset between the clean model and a target model that misclassifies the subpopulation, and a subpopulation is much easier to attack if the loss difference is small. This property also generalizes to high-dimensional benchmark datasets. For the Adult benchmark dataset, we show that we can find semantically-meaningful subpopulation properties that are related to the susceptibilities of a selected group of subpopulations. The results in this paper are accompanied by a fully interactive web-based visualization of subpopulation poisoning attacks found at https://uvasrg.github.io/visualizing-poisoning/.

# Summary. An optional shortened abstract.
summary: We introduce a method to manipulate neuron activations while pre-training models, allowing highly successful inference of sensitive properties of the victim's downstream training data.

tags: ["data poisoning attacks", "subpopulation poisoning attacks", "variation in susceptibility"]

# Display this page in the Featured widget?
# featured: true

# Custom links (uncomment lines below)
# links:
# - name: Custom Link
#   url: http://example.org

url_pdf: 'https://arxiv.org/abs/2311.11544'
url_code: 'https://uvasrg.github.io/visualizing-poisoning/'
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
