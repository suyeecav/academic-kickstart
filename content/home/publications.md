---
# An instance of the Featured Content widget.
# Documentation: https://wowchemy.com/docs/page-builder/
widget: featured

# This file represents a page section.
headless: true

# Order that this section appears on the page.
weight: 40

title: Selected Publications
subtitle: ''

# To feature a paper here, set `featured: true` in its
# `content/publication/<name>/index.md`. Everything else still shows
# on the full publication list at /publication/.

content:
  # Page type to display. E.g. post, talk, publication...
  page_type: publication
  # Choose how many pages you would like to display (0 = all pages)
  count: 0
  # Page order: descending (desc) or ascending (asc) date.
  order: desc
  filters:
    tag: ''
    category: ''
    publication_type: ''
    author: ''
    exclude_featured: false
  archive:
    enable: true
    text: All publications
    link: /publication/

design:
  # Choose a view for the listings:
  #   1 = List
  #   2 = Compact
  #   3 = Card
  #   4 = Citation
  view: 4
  columns: '1'
---
