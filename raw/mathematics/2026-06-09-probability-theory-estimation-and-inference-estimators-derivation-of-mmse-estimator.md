---
source: "KaedeSync/_Knowledge/Mathematics/Probability Theory/Estimation and Inference/Estimators/Derivation of MMSE Estimator.md"
ingested: 2026-06-09
---

To derive the optimal estimate of [[Minimum Mean Squared Error Estimation]], we need the conditional distribution of $\mathbf{\theta}$ given $\mathbf{x}$, $p(\mathbf{\theta}|\mathbf{x})$, which will be obtained from [[Bayes Theorem]]
$$
p(\mathbf{\theta}|\mathbf{x})=\frac{{p(\mathbf{x}|\mathbf{\theta})p(\mathbf{\theta})}}{p(\mathbf{x})}
$$
The MSE can then be derived as
$$
J=\mathbb{E}[(\hat{\mathbf{\theta}}-\mathbf{\theta})^{2}]=\int_{\theta}(\hat{\theta}-\theta)^{2}p(\theta|\mathbf{x})d\theta
$$
Differentiation with respect to $\hat{\theta}$ gives
$$
\begin{align}
\frac{{\partial J}}{\partial \hat{\theta}} & =\frac{d}{d\hat{\theta}}\int_{\theta}(\hat{\theta}-\theta)^{2}p(\theta|\mathbf{x})d\theta \\
 & =\int_{\theta}\frac{d}{d\hat{\theta}}(\hat{\theta}-\theta)^{2}p(\theta|\mathbf{x})d\theta \\
 & =\int_{\theta}2(\hat{\theta}-\theta)p(\theta|\mathbf{x})d\theta
\end{align}
$$
Setting to zero, we get a stationary point
$$
\begin{align}
\int_{\theta}\hat{\theta}p(\theta|\mathbf{x})d\theta & =\int_{\theta}\theta p(\theta|\mathbf{x})d\theta \\
\hat{\theta}\left(\int_{\theta}p(\theta|\mathbf{x})d\theta\right) & =\mathbb{E}[\theta|\mathbf{x}] \\
\hat{\theta}^{\text{MMSE}} & =\mathbb{E}[\theta|\mathbf{x}]
\end{align}
$$
