+++
title = "Peaks Over Threshold for Bursty Time Series"
date = 2018-04-28T00:00:00

# Authors. Comma separated list, e.g. `["Bob Smith", "David Jones"]`.
authors = ["Katharina Hees, Smarak Nayak, Peter Straka"]

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
publication = "preprint arXiv:1802.05218"
publication_short = "arXiv:1802.05218"

# Abstract and optional shortened version.
abstract = "In many complex systems studied in statistical physics, inter-arrival times between events such as solar flares, trades and neuron voltages follow a heavy-tailed distribution. The set of event times is fractal-like, being dense in some time windows and empty in others, a phenomenon which has been dubbed 'bursty'. This article generalizes the Peaks Over Threshold (POT) model to the setting where inter-event times are heavy-tailed. For high thresholds and infinite-mean waiting times, we show that the times between threshold crossings are Mittag-Leffler distributed, and thus form a 'fractional Poisson Process' which generalizes the standard Poisson Process. We provide graphical means of estimating model parameters and assessing model fit. Along the way, we apply our inference method to a real-world bursty time series, and show how the memory of the Mittag-Leffler distribution affects the predictive distribution for the time until the next extreme event."
abstract_short = ""

# Featured image thumbnail (optional)
image_preview = ""

# Is this a selected publication? (true/false)
selected = true

# Projects (optional).
#   Associate this publication with one or more of your projects.
#   Simply enter the filename (excluding '.md') of your project file in `content/project/`.
projects = ["bursts"]

# Links (optional).
url_pdf = ""
url_preprint = ""
url_code = "https://github.com/strakaps/bursty-POT"
url_dataset = ""
url_project = ""
url_slides = ""
url_video = ""
url_poster = ""
url_source = ""

# Custom links (optional).
#   Uncomment line below to enable. For multiple links, use the form `[{...}, {...}, {...}]`.
url_custom = [
    {name = "HTML", url = "https://strakaps.github.io/bursty-POT"}, 
    {name = "arXiv", url = "https://arxiv.org/abs/1802.05218"}
]

# Does the content use math formatting?
math = true

# Does the content use source code highlighting?
highlight = true

# Featured image
# Place your image in the `static/img/` folder and reference its filename below, e.g. `image = "example.jpg"`.
[header]
image = "bursty-POT.png"
caption = ""

+++
