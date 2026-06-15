---
source: KaedeSync/_Knowledge/Machine Learning/Deep Learning/Layer Normalisation.md
ingested: 2026-06-08
---

Define normalisation layer on vector $\mathbf{z} \in \mathbb{R}^{D}$:
$$
N(\mathbf{z})_{i}=\frac{{\mathbf{z}_{i}-\text{mean}(\mathbf{z})}}{\text{std}(\mathbf{z})+\epsilon}
$$
where
$$
\begin{align}
\text{mean}(\mathbf{z}) & =\frac{1}{D}\mathbf{z}^{T}\mathbf{1} \\
\text{std}(\mathbf{z}) & =\sqrt{ \frac{1}{D}\sum_{i}(\mathbf{z}_{i}-\text{mean}(\mathbf{z}))^{2} }
\end{align}
$$
[[Deep Learning]]