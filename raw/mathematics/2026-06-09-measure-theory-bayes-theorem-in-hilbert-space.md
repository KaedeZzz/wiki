---
source: "KaedeSync/_Knowledge/Mathematics/Measure Theory/Bayes Theorem in Hilbert Space.md"
ingested: 2026-06-09
---

In infinite dimensional [[Hilbert Space]], the densities from [[Bayes Theorem]] cannot be obtained.

However, the [[Radon-Nikodym Derivative]] between a posterior measure $\mu^{y}$ and a prior measure $\mu^{0}$ can define the corresponding likelihood function:
$$
\frac{d\mu^{y}}{d\mu_{0}}\propto P(y|u)
$$
The reference measure for a Hilbert space is the [[Gaussian Measure]], so $\mu^{0}=\mathcal N(m, c)$, which formally defines a [[Gaussian Process]] prior.