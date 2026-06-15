---
source: KaedeSync/_Knowledge/Machine Learning/Deep Learning/Autoencoders/Principal Component Analysis.md
ingested: 2026-06-08
---

Project the data to the largest principal axes (principal component).

Calculate:
1. Calculate [[Covariance Matrix]]
2. Solve for eigenvalues and eigenvectors of covariance matrix
$$
\begin{bmatrix}
\sigma_{x}^{2} & \sigma_{xy} \\
\sigma_{xy} & \sigma_{y}^{2}
\end{bmatrix}
\begin{bmatrix}
v_{x} \\
v_{y} 
\end{bmatrix}
=\lambda
\begin{bmatrix}
v_{x} \\
v_{y}
\end{bmatrix}
$$
Essentially a [[Singular Value Decomposition]]

Why use PCA? -> fast, interpretable
1. Only rely on basic linear algebra, so very fast. $$\begin{aligned}
\text{Complexity} &= O(nd^{2}+d^{3})\\n&=\text{ Number of samples}\\d&=\text{ Number of features}
\end{aligned}$$Complexity is linear with dataset size.
2. Eigenvalue tells importance of each latent space dimension.
Not good at processing non-linear data.