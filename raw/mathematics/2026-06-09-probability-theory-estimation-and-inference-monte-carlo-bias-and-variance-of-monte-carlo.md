---
source: "KaedeSync/_Knowledge/Mathematics/Probability Theory/Estimation and Inference/Monte Carlo/Bias and Variance of Monte Carlo.md"
ingested: 2026-06-09
---

Let the [[Monte Carlo]] estimator be
$$
\mathbb{E}[h(\mathbf{x})]\approx \frac{1}{N}\sum_{\alpha=1}^{N}h(\mathbf{x})
$$
bias:
$$
\mathbb{E}\left[\frac{1}{N}\sum_{\alpha=1}^{N}h(\mathbf{x})\right]=\frac{1}{N}\sum_{\alpha=1}^{N}\mathbb{E}[h(\mathbf{x})]=\mathbb{E}[h(\mathbf{x})]
$$
so it is unbiased.

Variance:
$$
\begin{align}
 & \mathbb{E}\left[ \left( \frac{1}{N}\sum_{\alpha=1}^{N}h(\mathbf{x})-\mu \right)^{2} \right] \\
 & =\mathbb{E}\left[ \frac{1}{N^{2}}\sum_{\alpha=1}^{N}h(\mathbf{x})-\mu TBD \right]
\end{align}
$$