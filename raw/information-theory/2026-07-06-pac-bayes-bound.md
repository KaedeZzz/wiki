---
source: KaedeSync/_Knowledge/Information Theory/PAC-Bayes Bound.md
ingested: 2026-07-06
---

[[Deep Learning]]
expected loss on future data:
$$
L_{p}\leq \frac{1}{1-\frac{1}{2\beta}}\left( \mathbb{E}_{w}L_{\mathcal D}+ \frac{\beta}{N}KL(q(w|\mathcal D)||p(w))\right)
$$
where $L_{p}$ is the expected loss and $L_{\mathcal D}$ is the past (empirical) loss.
$p(w)$ is the prior distribution of weights and $q(w)$ is the posterior distribution of weights after seen dataset. The gap between the two measures generalisation error.

However if we consider that the posterior is a delta function (weights converge), the KL divergence will go to infinity. That is called vacuous bound. Not useful.

In fact, some weights are highly critical and many are "uninformative", meaning those weights can be changed easily without changing the results, so we can think of the **posterior** distribution as a multivariate Gaussian, centred around the converged weight, with some very thin dimensions (even though the training process might be deterministic).

Minimum KL divergence obtained when $p(w)$ is the marginal of weights over all datasets. If this is the case, then KL divergence will become Shannon mutual information between weights and dataset.