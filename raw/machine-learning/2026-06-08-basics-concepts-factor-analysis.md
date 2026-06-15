---
source: KaedeSync/_Knowledge/Machine Learning/Basics/Concepts/Factor Analysis.md
ingested: 2026-06-08
---

A low-dimensional manifold representation with continuous latent variable.

Intuition:
- The observed high-dimensional vector $x$ is generated from a small hidden vector $z$, then corrupted by independent noise.

The model is represented as:
$$
\begin{align}
p(\mathbf{z}) & =\mathcal{N}(\mathbf{z};\mathbf{0},\mathbf{I}) \\
 p(\mathbf{x}|\mathbf{z}) & =\mathcal{N}(\mathbf{x};\mathbf{Cz},\mathbf{\Sigma}_{\text{diag}})
\end{align}
$$
where:
- the latent variable $z$ is low-dimensional,
- $C$ is the loading matrix,
- $\Sigma_{\text{diag}}$ is diagonal noise covariance.

Note that, mean of observation is a linear transformation of latent variable.

As all elements are Gaussian, a closed-form solution is:
$$
p(\mathbf{x})=\int p(\mathbf{x}|\mathbf{z})p(\mathbf{z})d\mathbf{z}=\mathcal{N}(\mathbf{x};\mathbf{0},\mathbf{CC}^{T}+\mathbf{\Sigma}_{\text{diag}})
$$

If $\mathbf{\Sigma}_{\text{diag}}=\sigma ^{2}\mathbf{I}$, then the model is probabilistic [[Principal Component Analysis]].