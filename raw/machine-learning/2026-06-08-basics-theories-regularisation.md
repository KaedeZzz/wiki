---
source: KaedeSync/_Knowledge/Machine Learning/Basics/Theories/Regularisation.md
ingested: 2026-06-08
---

Regularisation is methods to reduce the generalisation gap, technically means adding terms to loss function.

Regularised loss:
$$
\theta^{*}=\arg\min_{\theta}\left[ \sum_{i}L(f(\hat{x}_{i};\theta),y_{i})-\log p(\theta) \right]
$$
where $p(\theta)$ is the prior, representing a preference to some parameters. The regulariser acts as an extra preference on parameters.

[[Machine Learning]]