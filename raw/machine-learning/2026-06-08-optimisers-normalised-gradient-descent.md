---
source: KaedeSync/_Knowledge/Machine Learning/Optimisers/Normalised Gradient Descent.md
ingested: 2026-06-08
---

measure mean and point-wise squared gradient.
$$
\begin{align}
\mathbf{m}_{t+1} & =\frac{{\partial L(\theta)}}{\partial \theta} \\
\mathbf{v}_{t+1} & =\left( \frac{{\partial L(\theta)}}{\partial \theta} \right)^{2} \\
\theta_{t+1} & =\theta_{t}-\alpha  \frac{\mathbf{m}_{t+1}}{\sqrt{ \mathbf{v}_{t+1} }+\mathbf{\epsilon}}
\end{align}
$$
where $\sqrt{ \mathbf{v} }$ is point-wise as well.

[[Gradient Descent]]