---
source: KaedeSync/_Knowledge/Machine Learning/Basics/Concepts/Clustering.md
ingested: 2026-06-08
---

[[Machine Learning]]

**What is clustering?**
- two points belonging to the same cluster are generally more similar to each other or closer to each other than two points belonging to different clusters.
- unsupervised learning problem.
- goal: find a proper clustering rule.

**Formal Definition**
We can formalise a vector quantiser in terms of an *assignment* rule $\mathbf{x}\to k(\mathbf{x})$ for assigning datapoints $\mathbf{x}$ to one of $K$ codenames, and a *reconstruction* rule $k\to \mathbf{m}^{(k)}$, the aim being to choose the functions $k(\mathbf{x})$ and $\mathbf{m}^{(k)}$ to minimise the expected distortion being
$$
D=\sum_{\mathbf{x}}P(\mathbf{x}) \frac{1}{2}[\mathbf{m}^{(k(x))}-\mathbf{x}]^{2}
$$
We do not necessarily believe that the templates $\{ \mathbf{m}^{(k)} \}$ has a meaning.