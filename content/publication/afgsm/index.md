---
title: "Scalable Attack on Graph Data by Injecting Vicious Nodes"

# Authors
# If you created a profile for a user (e.g. the default `admin` user), write the username (folder name) here 
# and it will be replaced with their full name and linked to their profile.
authors:
- Jihong Wang
- Minnan Luo
- admin
- Jundong Li
- Zijiang Yang
- Qinghua Zheng

# Author notes (optional)
# author_notes:
# - "Equal contribution"
# - "Equal contribution"


date: # "2020-05-01T00:00:00Z"
doi: ""

# Schedule page publish date (NOT publication's date).
publishDate: "2010-05-01T00:00:00Z" # "2020-05-01T00:00:00Z"

# Publication type.
# Legend: 0 = Uncategorized; 1 = Conference paper; 2 = Journal article;
# 3 = Preprint / Working Paper; 4 = Report; 5 = Book; 6 = Book section;
# 7 = Thesis; 8 = Patent
publication_types: ["1"]

# Publication name and optional abbreviated publication name.
publication: In *European Conference on Machine Learning and Principles and Practice of Knowledge Discovery in Databases, 2020*
publication_short: In *ECML-PKDD 2020*

abstract: Recent studies have shown that graph convolution networks (GCNs) are vulnerable to carefully designed attacks, which aim to cause misclassification of a specific node on the graph with unnoticeable perturbations. However, a vast majority of existing works cannot handle large-scale graphs because of their high time complexity. Additionally, existing works mainly focus on manipulating existing nodes on the graph, while in practice, attackers usually do not have the privilege to modify information of existing nodes. In this paper, we develop a more scalable framework named Approximate Fast Gradient Sign Method (AFGSM) which considers a more practical attack scenario where adversaries can only inject new vicious nodes to the graph while having no control over the original graph. Methodologically, we provide an approximation strategy to linearize the model we attack and then derive an approximate closed-from solution with a lower time cost. To have a fair comparison with existing attack methods that manipulate the original graph, we adapt them to the new attack scenario by injecting vicious nodes. Empirical experimental results show that our proposed attack method can significantly reduce the classification accuracy of GCNs and is much faster than existing methods without jeopardizing the attack performance.

# Summary. An optional shortened abstract.
summary: We propose a scalable attack that generates adversarial examples on extremely large graphs targeting graph neural networks.

tags: ["adversarial examples", "graph neural networks", "scalable attacks"]

# Display this page in the Featured widget?
# featured: true

# Custom links (uncomment lines below)
# links:
# - name: Custom Link
#   url: http://example.org

url_pdf: 'https://arxiv.org/abs/2004.13825'
url_code: 'https://github.com/wangjh-github/AFGSM'
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
