---
source: "KaedeSync/_Knowledge/Mathematics/Probability Theory/Estimation and Inference/Basics/Minimum Mean Squared Error Estimation.md"
ingested: 2026-06-09
---

Given some data $\mathbf{x}$ we attempt to find an estimator $\hat{\mathbf{\theta}}(\mathbf{x})$ which has minimum squared error on average:
$$
\min_\hat{\mathbf{\theta}} \mathbb{E}[(\hat{\mathbf{\theta}}-\mathbf{\theta})^{2}]
$$
such that the estimator is
$$ 
\hat\theta_{\text{MMSE}}(x)=\mathbb E[\Theta|X=x]=\int\theta f_{\Theta|X}(\theta|x)d\theta 
$$
[[Estimation and Inference]]