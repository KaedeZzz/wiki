---
source: "KaedeSync/_Knowledge/Mathematics/Probability Theory/Estimation and Inference/Linear Models/General Linear Model (GLM).md"
ingested: 2026-06-09
---

[[Estimation and Inference]]

In the linear model it is assumed that the data $x$ is generated as a linear function of the parameters $\theta$ with an additive random modelling error term $e_{n}$:
$$
\mathbf{}x_{n}=g_{n}^{T}\theta+e_{n}
$$
where $g_{n}$ is a $P$-dimensional column vector.

Therefore, the expression may be written for the whole vector $\mathbf{x}$ as
$$
\mathbf{x}=\mathbf{G\theta}+\mathbf e
$$
where
$$
\mathbf G=\begin{bmatrix}
g_{0}^{T} \\
g_{1}^{T} \\
\vdots \\
g_{N-1}^{T}
\end{bmatrix}
$$
Choice of the matrix $\mathbf G$ will lead to a wide range of possible models.