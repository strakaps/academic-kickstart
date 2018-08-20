+++
title = "Variable Order Fractional Fokker-Planck Equations derived from Continuous Time Random Walks"
date = 2018-08-01T00:00:00

# Authors. Comma separated list, e.g. `["Bob Smith", "David Jones"]`.
authors = ["Peter Straka"]

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
publication = "Physica A: Statistical Mechanics and its Applications. DOI: [10.1016/j.physa.2018.03.010](https://doi.org/10.1016/j.physa.2018.03.010)"
publication_short = "Physica A"

# Abstract and optional shortened version.
abstract = "Continuous Time Random Walk models (CTRW) of anomalous diffusion are studied, where the anomalous exponent β(x)∈(0,1) varies in space. This type of situation occurs e.g. in biophysics, where the density of the intracellular matrix varies throughout a cell. Scaling limits of CTRWs are known to have probability distributions which solve fractional Fokker-Planck type equations (FFPE). This correspondence between stochastic processes and FFPE solutions has many useful extensions e.g. to nonlinear particle interactions and reactions, but has not yet been sufficiently developed for FFPEs of the 'variable order' type with non-constant β(x). In this article, variable order FFPEs (VOFFPE) are derived from scaling limits of CTRWs. The key mathematical tool is the 1-1 correspondence of a CTRW scaling limit to a bivariate Langevin process, which tracks the cumulative sum of jumps in one component and the cumulative sum of waiting times in the other. The spatially varying anomalous exponent is modelled by spatially varying β(x)-stable Levy noise in the waiting time component. The VOFFPE displays a spatially heterogeneous temporal scaling behaviour, with generalized diffusivity and drift coefficients whose units are length2/timeβ(x) resp. length/timeβ(x). A global change of the time scale results in a spatially varying change in diffusivity and drift. A consequence of the mathematical derivation of a VOFFPE from CTRW limits in this article is that a solution of a VOFFPE can be approximated via Monte Carlo simulations. Based on such simulations, we are able to confirm that the VOFFPE is consistent under a change of the global time scale."
abstract_short = ""

# Featured image thumbnail (optional)
image_preview = "https://raw.githubusercontent.com/strakaps/variable-order-MC/master/densities.png"

# Is this a selected publication? (true/false)
selected = true

# Projects (optional).
#   Associate this publication with one or more of your projects.
#   Simply enter the filename (excluding '.md') of your project file in `content/project/`.
projects = ["anomalous-diffusion"]

# Links (optional).
url_pdf = ""
url_preprint = ""
url_code = "https://github.com/strakaps/variable-order-MC"
url_dataset = ""
url_project = ""
url_slides = ""
url_video = ""
url_poster = ""
url_source = ""

# Custom links (optional).
#   Uncomment line below to enable. For multiple links, use the form `[{...}, {...}, {...}]`.
url_custom = [
    {name = "DOI", url = "https://doi.org/10.1016/j.physa.2018.03.010"}, {name = "arXiv", url = "https://arxiv.org/abs/1712.06767"}
]


# Does the content use math formatting?
math = true

# Does the content use source code highlighting?
highlight = true

# Featured image
# Place your image in the `static/img/` folder and reference its filename below, e.g. `image = "example.jpg"`.
[header]
image = "https://raw.githubusercontent.com/strakaps/variable-order-MC/master/densities.png"
caption = ""

+++
