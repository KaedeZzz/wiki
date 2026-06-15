---
source: KaedeSync/_Knowledge/Machine Learning/Gaussian Process/Matérn Covariance Functions.md
ingested: 2026-06-08
---

Stationary covariance functions can be based on the Matérn form:
$$
k(\mathbf{x},\mathbf{x}')=\frac{1}{\Gamma(\nu)2^{\nu-1}}\left[ \frac{\sqrt{ 2\nu }}{l}\lvert \mathbf{x}-\mathbf{x}' \rvert  \right]^{\nu}K_{\nu}\left(\frac{\sqrt{ 2\nu }}{l}\lvert \mathbf{x}-\mathbf{x}' \rvert \right)
$$
where $K_{\nu}$ is the modified Bessel function of second kind of order $\nu$, and $l$ is the characteristic length scale.

Sample functions from Matérn froms are $\lfloor \nu-1 \rfloor$ times differentiable; thus, the hyperparameter $\nu$ can control the degree of smoothness.