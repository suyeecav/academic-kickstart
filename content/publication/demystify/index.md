---
title: "Demystifying Hidden Privacy Settings in Mobile Apps"

# Authors
# If you created a profile for a user (e.g. the default `admin` user), write the username (folder name) here 
# and it will be replaced with their full name and linked to their profile.
authors:
- Yi Chen
- Mingming Zha
- Nan Zhang
- Dandan Xu 
- Qianqian Zhao 
- Xuan Feng 
- Kan Yuan
- admin 
- Yuan Tian 
- Kai Chen 
- XiaoFeng Wang
- Wei Zou

# Author notes (optional)
# author_notes:
# - "Equal contribution"
# - "Equal contribution"

date:  "2019-01-01T00:00:00Z"
doi: ""

# Schedule page publish date (NOT publication's date).
publishDate:  "2019-01-01T00:00:00Z"

# Publication type.
# Legend: 0 = Uncategorized; 1 = Conference paper; 2 = Journal article;
# 3 = Preprint / Working Paper; 4 = Report; 5 = Book; 6 = Book section;
# 7 = Thesis; 8 = Patent
publication_types: ["1"]

# Publication name and optional abbreviated publication name.
publication: In *IEEE Symposium on Security and Privacy, 2019*
publication_short: In *IEEE S&P 2019*

abstract: Mobile apps include privacy settings that allow their users to configure how their data should be shared. These settings, however, are often hard to locate and hard to understand by the users, even in popular apps, such as Facebook. More seriously, they are often set to share user data by default, exposing her privacy without proper consent. In this paper, we report the first systematic study on the problem, which is made possible through an in-depth analysis of user perception of the privacy settings. More specifically, we first conduct two user studies (involving nearly one thousand users) to understand privacy settings from the user’s perspective, and identify these hard-to-find settings. Then we select 14 features that uniquely characterize such hidden privacy settings and utilize a novel technique called semantics- based UI tracing to extract them from a given app. On top of these features, a classifier is trained to automatically discover the hidden privacy settings, which together with other innovations, has been implemented into a tool called Hound. Over our labeled data set, the tool achieves an accuracy of 93.54%. Further running it on 100,000 latest apps from both Google Play and third-party markets, we find that over a third (36.29%) of the privacy settings identified from these apps are “hidden”. Looking into these settings, we observe that they become hard to discover and hard to understand primarily due to the problematic categorization on the apps’ user interfaces and/or confusing descriptions. Further importantly, though more privacy options have been offered to the user over time, also discovered is the persistence of their usability issue, which becomes even more serious, e.g., originally easy-to-find settings now harder to locate. And among all such hidden privacy settings, 82.16% are set to leak user privacy by default. We provide suggestions for improving the usability of these privacy settings at the end of our study.

# Summary. An optional shortened abstract.
summary: We conduct a systematic study of the privacy risks arising from default privacy settings in mobile applications.

tags: ["user privacy", "user study", "mobile applications"]

# Display this page in the Featured widget?
# featured: true

# Custom links (uncomment lines below)
# links:
# - name: Custom Link
#   url: http://example.org

url_pdf: 'https://ieeexplore.ieee.org/stamp/stamp.jsp?arnumber=8835388'
url_code: ''
url_dataset: ''
url_poster: ''
url_project: ''
url_slides: ''
url_source: ''
url_video: 'https://youtu.be/sf-xzsoV3Tk?feature=shared'

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
