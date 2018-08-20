+++
# Date this page was created.
date = 2016-04-27T00:00:00

# Project title.
title = "Identifying antidepressant users with depression"

# Project summary to display on homepage.
summary = "Only 1/2 -- 2/3 of antidepressant users have depression. How do we use statistical learning to predict depression given antidepressant use?"

# Optional image to display on homepage (relative to `static/img/` folder).
image_preview = "coefs_cutoff.png"

categories = ["Healthcare"]
# Tags: can be used for filtering projects.
# Example: `tags = ["machine-learning", "deep-learning"]`
tags = ["Statistics", "Healthcare", "R"]

# Optional external URL for project (replaces project detail page).
external_link = ""

# Does the project detail page use math formatting?
math = false

# Optional featured image (relative to `static/img/` folder).
[header]
image = "headers/coefs_cutoff-wide.png"
caption = "Effect sizes for drug interactions"

+++

Records of antidepressant dispensings are often used in public health research
as a surrogate measure of depression.  In 1/3 to 1/2 of cases however,
antidepressants are prescribed for indications other than depression,
which results in misclassification.

Medicare Benefits Schedule (MBS) data contain the dispensings of antidepressants
and other pharmaceuticals, and data from the 45 and Up Study provide a gold
standard response variable
(a yes/no answer to "Have you been treated for depression?").

How can these data be used to design a predictive algorithm identifying
antidepressant users _with_ depression?
