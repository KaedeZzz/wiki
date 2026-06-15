---
source: "KaedeSync/_Knowledge/Mathematics/Probability Theory/Estimation and Inference/Estimators/Discriminative Model Estimation.md"
ingested: 2026-06-09
---

[[Estimation and Inference]]
For discriminative model, we can generate predictions from:
$$
\hat{\omega}=\arg\max_{\omega}\{ P(\omega|x^{*},\theta) \}
$$
therefore we need to find $\theta$. One plausible way is via Maximum Likelihood Estimation.
$$
\hat{\theta}=\arg\max_{\theta}\left\{  \sum_{i=1}^{N}\log(P(y_{i}|x_{i},\theta))  \right\}
$$
(Assume all training samples independent)
Decision boundaries are therefore where class posteriors are the same.