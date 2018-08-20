+++
# Date this page was created.
date = 2018-05-14

# Project title.
title = "Networks of Health Providers"

# Project summary to display on homepage.
summary = "What effect does the social structure of health systems have on health outcomes?"

# Optional image to display on homepage (relative to `static/img/` folder).
image_preview = "big-bipartite.png"

categories = ["public-health"]
# Tags: can be used for filtering projects.
# Example: `tags = ["machine-learning", "deep-learning"]`
tags = ["public-health", "python", "networks", "big data"]

# Optional external URL for project (replaces project detail page).
external_link = ""

# Does the project detail page use math formatting?
math = false

# Optional featured image (relative to `static/img/` folder).
[header]
image = "headers/big-bipartite-wide.png"
caption = "Hierarchical bipartite network of General Practitioners and their patients"

+++

* What is the network structure of healthcare providers and their 
practices/clinics?
* What is their patient sharing pattern? 
* Does sharing of patient information between providers lead to better health 
outcomes?
* Do practice size and patient sharing behaviour influence the quality of 
healthcare?

Australian Medicare claims data contains
data[^1] on tens of thousands of healthcare providers and millions of 
patients, such as patient characteristics
(age, sex, ...) 
and provider characteristics 
(specialty, type and frequency of services delivered, bulk-billing behaviour,  
...). 

[^1]: de-identified, of course. 

The natural structure of these data is a network, where 
providers & patients are connected whenever a service is provided. 
The structure of this network contains crucial information on the flow of 
information and the variation of healthcare quality, and thus allows to 
tackle questions of national importance such as the above. 
