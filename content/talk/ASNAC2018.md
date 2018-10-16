+++
title = "The Network Structure of General Practice in Australia"
date = 2017-11-27T08:00:00  # Schedule page publish date.
draft = false

# Talk start and end times.
#   End time can optionally be hidden by prefixing the line with `#`.
time_start = 2018-11-28T14:00:00
#time_end = 2030-06-01T15:00:00

# Abstract and optional shortened version.
abstract = """
Bich Tran, Peter Straka, Michael O Falster, Kirsty A Douglas, Thomas Britz and Louisa R Jorm

We have studied the organisation and characteristics of general practice in Australia, based on routinely collected Medicare claims data. The dataset comprises records for 1.7 Million Australians per year, collected over 21 years.

Patient sharing behaviour among General Practitioners (GPs) reveals "Provider Practice Communities" (PPCs), which resemble GP practices and clinics. Data on GP practices is scarce in Australia, and we have established a data driven way to cluster GPs into PPCs.

To be able to detect PPCs which comprise only a small number of doctors or even just a single GP, we needed to _avoid_ a projection of the bipartite network (of GPs and patients) to a unipartite network (GPs only); moreover, we needed to address the resolution limit problem for community detection in large networks. This was solved via fitting constrained hierarchical stochastic blockmodels using the Python package graph-tool.

Based on the detected PPCs, we were able to study characteristics of PPCs, such as patient sharing behaviour, bulk-billing behaviour and a new measure for continuity of care. The network structure of PPCs over GPs provides a promising new way of studying unwarranted statistical variation in Australia's healthcare system in future analyses.
"""

abstract_short = ""

# Name of event and optional event URL.
event = "The Third Annual Australian Social Network Analysis Conference 2018"
event_url = "https://www.ansna.org.au/asnac2018-about/"

# Location of event.
location = "Canberra, Australia"

# Is this a selected talk? (true/false)
selected = true

# Projects (optional).
#   Associate this talk with one or more of your projects.
#   Simply enter your project's filename without extension.
#   E.g. `projects = ["deep-learning"]` references `content/project/deep-learning.md`.
#   Otherwise, set `projects = []`.
projects = ["GP-networks"]

# Tags (optional).
#   Set `tags = []` for no tags, or use the form `tags = ["A Tag", "Another Tag"]` for one or more tags.
tags = ["networks", "Python"]

# Links (optional).
url_pdf = ""
url_slides = ""
url_video = ""
url_code = ""

# Does the content use math formatting?
math = true

# Does the content use source code highlighting?
highlight = true

# Featured image
# Place your image in the `static/img/` folder and reference its filename below, e.g. `image = "example.jpg"`.
[header]
image = "headers/big-bipartite-wide.png"
caption = "The ACT doctor-patient network"

+++

