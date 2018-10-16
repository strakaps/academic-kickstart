+++
title = "A Universal Algorithm for Continuous Time Random Walks Limit Distributions"
date = 2018-04-28T00:00:00

# Authors. Comma separated list, e.g. `["Bob Smith", "David Jones"]`.
authors = ["Gurtek Gill, Peter Straka"]

# Publication type.
# Legend:
# 0 = Uncategorized
# 1 = Conference proceedings
# 2 = Journal
# 3 = Work in progress
# 4 = Technical report
# 5 = Book
# 6 = Book chapter
publication_types = ["2"]

# Publication name and optional abbreviated version.
publication = "preprint arXiv:1808.05737"
publication_short = "arXiv:1808.05737"

# Abstract and optional shortened version.
abstract = """
In this article, we generalize the recent Discrete Time Random Walk (DTRW) algorithm, which was introduced for the computation of probability densities of fractional diffusion. Although it has the same computational complexity and shares the same desirable features (consistency, conservation of mass, strictly non-negative solutions), it applies to virtually every conceivable Continuous Time Random Walk (CTRW) limit process, which we define broadly as the limit of a sequence of jump processes with renewals at every jump. Our only restrictive assumption is the boundedness and continuity of coefficients of the underlying Langevin proceesses.

We highlight three main novel use-cases: i) CTRWs with spatially varying waiting times, eg for interface problems between two differently anomalous media; ii)(varying) temporal drift, which limits the short-time speed of subdiffusive processes; and iii) the computation of probability densities for generalized inverse subordinators.
"""

abstract_short = ""

# Featured image thumbnail (optional)
image_preview = ""

# Is this a selected publication? (true/false)
selected = true

# Projects (optional).
#   Associate this publication with one or more of your projects.
#   Simply enter the filename (excluding '.md') of your project file in `content/project/`.
projects = ["anomalous-diffusion"]

# Links (optional).
url_pdf = ""
url_preprint = ""
url_code = "https://github.com/strakaps/VaryExp"
url_dataset = ""
url_project = ""
url_slides = ""
url_video = ""
url_poster = ""
url_source = ""

# Custom links (optional).
#   Uncomment line below to enable. For multiple links, use the form `[{...}, {...}, {...}]`.
url_custom = [
    {name = "arXiv", url = "https://arxiv.org/abs/1808.05737"}
]

# Does the content use math formatting?
math = true

# Does the content use source code highlighting?
highlight = true

# Featured image
# Place your image in the `static/img/` folder and reference its filename below, e.g. `image = "example.jpg"`.
[header]
image = "headers/subordinators.png"
caption = ""

+++
