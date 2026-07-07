---
source: KaedeSync/_Knowledge/Communications/Filter Design/Filter Design by Optimisation.md
ingested: 2026-07-08
---

[[Digital Filtering]]

Given the ideal filter $H$ and the weighting function $W$ , find the optimal filter $G$ of length $N$ such that, given the error filter $E$
$$
E(\theta)=W(\theta)[H(\theta)-G(\theta)]
$$
$G$ minimises:
- The mean squared error
$$
\int_{-\pi}^{\pi}E^{2}(\theta)d\theta
$$
- or, the maximum error
$$
\sup_{-\pi\leq \theta\leq \pi}|E(\theta)|
$$
the latter known as "equiripple" filters.