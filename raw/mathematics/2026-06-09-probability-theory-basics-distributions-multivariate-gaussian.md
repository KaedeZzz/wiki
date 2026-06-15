---
source: "KaedeSync/_Knowledge/Mathematics/Probability Theory/Basics/Distributions/Multivariate Gaussian.md"
ingested: 2026-06-09
---

See: [[Gaussian Distribution]]
$$
\frac{1}{(2\pi)^{\frac{n}{2}}|\det \mathbf{C}|^{\frac{1}{2}}}\exp \left\{  -\frac{1}{2}(\mathbf{x}-\mathbf{m})\mathbf{C}^{-1}(\mathbf{x}-\mathbf{m})^T  \right\}
$$
$$
\begin{aligned}
m_{i}&=\mathbb{E}\{ x_{i} \}\text{ is the mean}\\
[\mathbf{C}_{i,j}]&=\mathbb{E}[(x_{i}-m_{i})(x_{j}-m_{j})]\text{ is the covariance matrix}
\end{aligned}
$$
In particular, we know:
- The marginals are Gaussian.
- $\mathbf{C}$ is diagonal $\leftrightarrow$ $\mathbf{x}$s are independent.

Note that: an [[Affine Transformation]] of Gaussian vector is still a Gaussian vector.
$$
\mathcal N(m,\mathbf{\Sigma})=m+\mathbf{SX}\text{ where }\mathbf{\Sigma}=\mathbf{SS}^T\text{ and }X_{i}=\mathcal N(0, 1)
$$
