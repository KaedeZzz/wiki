---
source: "KaedeSync/_Knowledge/Mathematics/Probability Theory/Estimation and Inference/Basics/Cost Function of Estimation 1.md"
ingested: 2026-06-09
---

Cost function $C(\hat{\theta},\theta)$ expresses the cost of estimating the parameter as $\hat{\theta}$ when the true value is $\theta$.
A suitable cost function is non-negative and usually satisfies $C(\theta,\theta)=0$.

We can write the expected cost over all of the unknown parameters, *conditional upon* the observed data $\mathbf{x}$:
$$
\mathbb{E}[C(\hat{\mathbf{\theta}},\mathbf{\theta})]=\int_{\mathbf{\theta}}C(\hat{\mathbf{\theta}},\mathbf{\theta})p(\mathbf{\theta}|\mathbf{x})d\mathbf{\theta}
$$

[[Estimation and Inference]]