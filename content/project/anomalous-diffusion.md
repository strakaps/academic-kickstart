+++
# Date this page was created.
date = 2016-04-27T00:00:00

# Project title.
title = "Continuous Time Random Walks"

# Project summary to display on homepage.
summary = "Limit theorems and statistical physics"

# Optional image to display on homepage (relative to `static/img/` folder).
image_preview = "anomalous-diffusion.png"

categories = ["Anomalous Diffusion"]
# Tags: can be used for filtering projects.
# Example: `tags = ["machine-learning", "deep-learning"]`
tags = ["Anomalous Diffusion"]

# Optional external URL for project (replaces project detail page).
external_link = ""

# Does the project detail page use math formatting?
math = false

# Optional featured image (relative to `static/img/` folder).
[header]
image = ""
caption = ""

+++

**Diffusion** is the net movement of molecules or atoms from a region of high
concentration to a region of low concentration
as a result of _random motion_ of the molecules or atoms
([Wikipedia](https://en.wikipedia.org/wiki/Diffusion)).

Due to a discovery by
[Einstein (1905)](https://doi.org/10.1002/andp.19053220806),
a universal model for the _random motion_ of microscopic particles
is Brownian motion, whose
[mean-squared displacement](https://en.wikipedia.org/wiki/Mean_squared_displacement)
increases linearly with time.

In many system with particles more complex than tiny molecules which interact
with their environment
(e.g. proteins, self-propelled bacteria or cells, stock market prices, ...)
the growth of the mean-squared displacement is no longer linear:

![anomalous-MSD](https://upload.wikimedia.org/wikipedia/commons/e/e6/Msd_anomalous_diffusion.svg) (Image credit Wikipedia).

The **Continuous Time Random Walk (CTRW)** is a model for anomalous diffusion:
it can model subdiffusion with long (heavy-tailed) waiting times between
steps, and superdiffusion with long (heavy-tailed) steps, and even a
mixture of both.

Scientists are interested in extending the CTRW model to allow for interactions
between walkers, and need tools for the computation of concentrations of
random walkers. Since the beginning of the century,
there has been a fruitful exchange
between statistical physics, experimental physics, pure mathematics and
computational mathematics, which has significantly advanced biophysics,
among other fields.
