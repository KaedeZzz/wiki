---
source: "KaedeSync/_Knowledge/Mathematics/Probability Theory/Estimation and Inference/Estimators/Multivariate Gaussian Class Conditional PDF.md"
ingested: 2026-06-09
---

Assume likelihood function be a multivariate Gaussian:
$$
p(x|\omega_{i},\theta_{i})=\mathcal N(x,\mu_{i},\Sigma_{i})
$$

![[Multivariate Gaussian]]

[[Maximum Likelihood Estimation]] estimates of the parameters given by:
$$
\begin{align}
\hat{\mu_{i}}&=\frac{\sum_{j:y_{j}=\omega_{i}}x_{j}}{\sum_{j:y_{j}=\omega_{i}}1} \\
\hat{\Sigma_{i}}&=\frac{\sum_{j:y_{j}=\omega_{i}}(x_{j}-\hat{\mu_{i}})(x_{j}-\hat{\mu_{i}})^{T}}{\sum_{j:y_{j}=\omega_{i}}1}
\end{align}
$$
