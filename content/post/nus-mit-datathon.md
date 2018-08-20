---
title: NUS-MIT Datathon
author: Peter Straka
date: '2018-07-10'
slug: nus-mit-datathon
categories:
  - events
tags:
  - data-science
  - healthcare
  - machine-learning
header:
  caption: '🤔'
  image: 'datathon.jpg'
---

Last week I had the privilege to participate in the
[NUS-NUH-MIT DATATHON](http://www.nus-datathon.com/)
and Workshop on applications of AI in healthcare with the
[UNSW Centre for Big Data Research in Health (CBDRH)](https://cbdrh.med.unsw.edu.au/)
team (Tim Churches, Mark Hanly, Oisin Fitzgerald and Oluwadamisola Sotade).


# Thu & Fri: Workshop & Talks

In the workshop
"Deploying AI Solutions in Real Clinical Practices" by
Dr Ngiam Kee Yuan (CTO, NUHS)
we discussed

* The large NUHS (National University Health System) databases and their storage structure
* Data security and ownership
* Applications for access to data
* The always changing standards of diagnosis codes (ICD9, ICD10, SNOMED, ...)
  and the problem of matching doctors diagnoses to these codes. In another talk,
  Hector Yee
  ([@eigenhector](https://twitter.com/eigenhector))
  shared some vice ideas on how to use word embeddings as a
  tool for matching hand-typed diagnoses to ICD10 codes.
* The importance of getting doctors to trust AI algorithms.
  Hector presented an interesting approach which iterates between an AI
  algorithm proposing codes and a doctor validating these.
  The goal is of course to _augment_ the doctors, not to _replace_ them.


# Fri - Sun: Datathon

## Friday 6pm: Pitching Topics & Forming Teams

23 clinicians pitch topics. We were most interested in a topic presented by
Dr Lui Pak Ling (Hematology) and Dr Stella Ang (Anesthesiology) at NUH:

Currently-used statistical models predicting the mortality risk of Intensive Care Unit (ICU)
patients assume that the importance of prognostic factors does not vary

Research Database, a large multi-centre critical care database made available by Philips Healthcare in partnership with the MIT Laboratory for Computational Physiology, they investigated whether the importance of prognostic factors varied in the course of each patient’s stay in ICU. Currently-used predictive models assume that they don’t vary.

> Currently, the mortality risk of ICU (intensive care unit) patients is assessed
based on a collection of variables at the time they are presented to the ICU
(the so-called
[Apache score](https://en.wikipedia.org/wiki/APACHE_II)). This score is assumed
to be the same _during the whole course of stay_ in the ICU.
Is this assumption appropriate, or does the importance of some prognostic variables
in fact change over time?

We joined forces with [Siqi Liu](https://www.mornin-feng.com/siqi),
a PhD student at Saw Swee Hock School of Public Health and
a member of the organising team for the Datathon who represented our team,
and [Peng Shen](https://www.linkedin.com/in/peng-shen-137568154/)
(MOH Holdings Pte Ltd). 

## All of Saturday: Extracting Data

We used the
[eICU Collaborative Research Database](https://eicu-crd.mit.edu/about/eicu/).
The organisers have made the data available via Google's BigQuery, which was
very quick and (almost) 100% reliable.
Working in pairs we extracted and cleaned various tables of variables
that we used as predictors:
comorbidity history, lab results, vitalperiodic and vitalaperiodic, coma score,
infusion drugs, dialysis, blood culture, mechanical ventilation, ...  

We queried the database using

* the [BigQuery](https://cloud.google.com/bigquery/quickstart-web-ui) web interface,
* the [Python API](https://pandas-gbq.readthedocs.io/en/latest/) and colab notebooks, or
* the [dbplyr](https://cran.r-project.org/web/packages/dbplyr/vignettes/dbplyr.html) package in R.


## Sunday morning: More wrangling

Joining all the extracted tables into one big table.
The final SQL query was 306 lines long and extracted
of 161,988 rows (a cohort of sepsis patients)
and 93 transformed and cleaned variables (categorical and continuous)
from tables with 224 million rows with 4-51 columns.


## Sunday 12pm-3pm:

#### Model fitting

As a baseline, we used logistic regression, with L1 penalty for variable
selection (using [glmnet](https://web.stanford.edu/~hastie/glmnet/glmnet_alpha.html)
in R). Virtually all rows had missing data,
so we need to impute by median.
This didn't seem to work out very well, as e.g. the variables picked at after
2 days in ICU had almost nothing in common with the variables picked for
3 or 4 days in ICU.

Gradient Boosting (using [catboost](https://tech.yandex.com/catboost/)
 in R) seemed to work stably with the
irregularly spaced, high-dimensional data with many missing values.
In our preliminary analysis, it seems that "age" may increase in importance
and "SaO2" (oxygen saturation) may decrease in importance.

#### Presentation writing:

Teams were judged on a three minute presentation only, and the time limit
was strictly enforced (our MC made the audience start clapping after
exactly 180 seconds). So the presentation had to be practiced to near
perfection, which Dami and Siqi succeeded in doing:
The judges placed us first in the track "AI for critical care" 🎉🎉🎉

![grinners](/img/datathon2.jpg)


# Work to be continued

So far, we have fitted individual models to each point in time
(day1, day2, ..., day5). This is of course not the ideal way to deal with
a longitudinal signal. One ought to try

* [Survival analysis with time-dependent coefficients](https://cran.r-project.org/web/packages/survival/vignettes/timedep.pdf)
* [Boosted multivariate trees for longitudinal data](https://rd.springer.com/article/10.1007/s10994-016-5597-1)

# The takeaway

Our team is walking away with a preliminary analysis on a cleaned dataset which is
likely to result in a publication, and 2 domain experts and 1 other data
scientist who are invested in continuing our work. I would say these two
days were incredibly well spent!
