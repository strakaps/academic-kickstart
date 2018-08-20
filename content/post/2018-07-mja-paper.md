---
title: "Big Networks in Healthcare"
author: Peter Straka
date: '2018-07-16'
slug: 2018-07-mja-paper
categories:
  - Public Health
tags:
  - Healthcare
  - Data Science
  - Publication
  - Machine Learning
header:
  caption: "Hierarchical blockmodel fitted and visualised using graph-tool. Doctors (top) are connected to patients (bottom) via a GP consultation recorded in MBS data."
  image: '/headers/big-bipartite-wide.png'
---

_See also the
[MJA podcast episode](https://www.mja.com.au/podcast/209/2/mja-podcasts-2018-episode-57-big-gp-data-research-prof-louisa-jorm-and-dr-michael)
accompanying this article._

Our joint work
([UNSW CBDRH](https://cbdrh.med.unsw.edu.au/) and
[Statistics](https://www.maths.unsw.edu.au/about/Statistics))
which analyses Australian patient claim data using big network algorithms
is now available on the
[MJA website](https://www.mja.com.au/journal/2018/209/2/overcoming-data-drought-exploring-general-practice-australia-network-analysis).
We have processed
[MBS](http://www.mbsonline.gov.au/internet/mbsonline/publishing.nsf/Content/Home)
claims data of 10% of Australians over the years 1994-2014, trying to shed light
on the following research questions:

1. What is the patient sharing behaviour of general practitioners (GPs): are there any
  meaningful clusters (called "Provider Practice Communities, PPC")
  of GPs which collaborate and share patients? How have these
  clusters changed in the course of 20 years?
2. How does Continuity of Care (CoC[^1]) differ between large and small
  PPCs?

[^1]: A patient typically seeing the same GP, or GP clinic, experiences high CoC:
    $${\rm CoC} = \frac{\max \left\lbrace n_k \right \rbrace}{\sum_k n_k}$$
    where $n_k$ are the numbers of visits made to different PPCs.

Datasets such as provided by
[BEACH](http://sydney.edu.au/medicine/Public Health/research/beach.php)
(Bettering the Evaluation And Care of Health, USYD)
would be ideal to tackle these questions, but were
[discontinued](http://sydney.edu.au/medicine/fmrc/media/FMRC-closure-2016-06.php)
due to lack of funding, and it may take several years until Australia's
[My Health Record](https://www.myhealthrecord.gov.au/)
is adopted by enough Australians to generate useful datasets.

Question 1 really is about the structure of information sharing in the Australian
health system. We believe we've found evidence of information sharing within clusters
of GPs (PPCs) which resemble the typical sizes of practices of GPs.
CoC is a proxy for the sharing of important patient information sharing,
which is believed to lead to better health outcomes;
but information sharing can also mean that GPs
have similar behaviour when referring to specialists or pathology
services, among which there may be low-value services such as unwarranted
surgical interventions and blood tests.

Based on the PPCs which we have identified,
**it is now possible to discover unwarranted variation of good and bad outcomes
on the level of PPCs (practices)**.
There are many interesting questions that can be tackled now, and
as a first step into this direction, we redefined "Continuity of Care"
on the PPC level, creating an indicator which is high if a patient is loyal
to the same practice, rather than the same GP.
It seems that the larger a practice, the less loyal patients are to individual
GPs; but if loyalty to the same practice is measured, small and large
practices seem to fare alike.


# Big Networks

The usual approach in network clustering
(which was seemingly taken by _all_ previous papers on this topic in the
medical literature)
is as follows:

1. Create a network of GPs only[^3], where patients only appear as weights
on the edges
(i.e. [project from bipartite to unipartite](https://en.wikipedia.org/wiki/Bipartite_network_projection)):
![projection](/img/Bipartite_network_projection.png)
<small> (source: [Wikipedia](https://en.wikipedia.org/wiki/Bipartite_network_projection#/media/File:Bipartite_network_projection.png)) </small>  

2. Cluster the GP nodes by maximizing[^4]
[modularity](https://en.wikipedia.org/wiki/Modularity_(networks)):
<img src="/img/modularity.jpg" width="300">
<small> (source: [sciencedirect](https://www.sciencedirect.com/science/article/pii/S1053811916306449)) </small>  

[^3]: In the graph shown, suppose X are the patients and Y the doctors; then the
    Y-projection is a network of doctors only, with edge weights computed from
    the number of shared patients.

[^4]: The picture shows the adjacency matrix, where each row and column
    corresponds to one node, and a black dot means there is an edge.
    The red squares represent a grouping of nodes.
    Modularity, in a nutshell, is the gain in the
    number of within-group edges achieved by the grouping,
    compared to the expected number if all edges were
    reassigned at random.

The main flaws with this approach are:

1. There is no good way to construct edge weights between GPs.[^2]
2. The
[resolution limit problem](https://en.wikipedia.org/wiki/Modularity_(networks)#Resolution_limit)
of modularity:
The minimum size of discoverable communities grows with the number of nodes
$N$ in the network, roughly like $\sqrt N$. Since we study thousands of GPs,
this problem is prohibitive.
3. Modularity assumes that all block structure is assortative, which can be
dangerous; moreover even
[completely random networks can have high modularity](https://journals.aps.org/pre/abstract/10.1103/PhysRevE.70.025101).

[^2]: If you go by the number of shared patients,
    this discards all patients which have
    only seen one GP, and makes it impossible to find single GPs.
    If you go by [Jaccard index](https://en.wikipedia.org/wiki/Jaccard_index),
    this leads to weights between 0 and 1, which is not useful for most
    community detection algorithms.

Using the Python package
[graph-tool](http://dx.doi.org/10.6084/m9.figshare.1164194),
we were able to:

1. Avoid the bipartite projection, even though this meant dealing with millions
    of nodes (patients and doctors) instead of thousands (doctors only).
2. Fit a
[hierarchical stochastic blockmodel](https://journals.aps.org/prx/abstract/10.1103/PhysRevX.4.011047),
which allows detecting much smaller communities.
Moreover, the block structure respected bipartiteness, meaning that each block
was made up of either doctors only or patients only.


# Computations

The main challenges were:

1. **Installing graph-tool:** pip and conda are not an option, you have to compile
  it from source, or install the native Linux / MacOS X packages.
2. **RAM usage:** graph-tool needed up to 64GB of RAM.
  We've used the
  [Katana computational cluster](https://www.hpc.science.unsw.edu.au/)
  at UNSW and got excellent support along the way.
3. **Numerous runs:** The hierarchical blockmodelling algorithm converges to
  a different solution every time; to be somewhat confident to have found a
  good minimum of the description length, we needed 4 runs of up to 6 hours
  each, for each of 5 regions.


# GitHub Repository

The full Python code used for this project, as well as more details on the
blockmodelling approach, can be found on the
[CBDRH GitHub page](https://github.com/CBDRH/GP-networks).


# Conclusion

Using hierarchical stochastic blockmodelling, it is possible to use data
which is routinely collected by GPs to monitor characteristics of Australian
general practices. Future research will clarify how these characteristics affect
patient care.
