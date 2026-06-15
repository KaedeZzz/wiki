---
source: KaedeSync/_Knowledge/Machine Learning/Expectation-Maximisation/Soft K-means Clustering.md
ingested: 2026-06-08
---

The responsibility function, in comparison to normal [[K-means Clustering]], is:
$$
r_{k}^{(n)}=\frac{{\exp(-\beta d(\mathbf{m}^{(k)},\mathbf{x}^{(n)}))}}{\sum_{k'}\exp(-\beta d(\mathbf{m}^{(k')},\mathbf{x}^{(n)}))}
$$
where $d$ denotes the distance.
(Kinda like [[Softmax Function]]. Maybe more computationally expensive?)