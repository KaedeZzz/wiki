---
source: "KaedeSync/_Knowledge/Mathematics/Probability Theory/Estimation and Inference/Estimators/Control Variates.md"
ingested: 2026-06-09
---

**What would we do in estimation if we have additional information** in the form of another function?

Let us say that we want to estimate $\mathbb{E}\{f(X)\}$ and we have another function $g(X)$ that we know of true expectation $\mathbb{E}\{g(X)\}$. Denote [[Monte Carlo]] estimations to $\mathbb{E}\{f(X)\}$ and $\mathbb{E}\{g(X)\}$ as $\hat{E}_{f}$ and $\hat{E}_{g}$.  $\hat{E}_{f}$ and $\hat{E}_{g}$ has association in that $\text{Cov}(\hat{E}_{f},\hat{E}_{g})\neq 0$.
*How would that happen?* #WHY

We construct a new **unbiased** estimator for $f$:
$$
\hat{E}^{c}_{f}=\hat{E}_{f}+c(\hat{E}_{g}-\mathbb{E}\{g(X)\})
$$
where parameter $c$ controls the quality of estimation, and $\mathbb{E}\{g(X)\}$ can be seen here as a constant.
Variance of the new estimator:
$$
\text{Var}(\hat{E}^{c}_{f})=\text{Var}(\hat{E}_{f})+c^{2}\text{Var}(\hat{E}_{g})+2c\text{Cov}(\hat{E}_{f},\hat{E}_{g})
$$
Find minimum variance by calculus:
$$
\frac{\partial\text{Var}(\hat{E}^{c}_{f})}{\partial c}\rvert_{\hat{c}_{opt}}=0\implies  \hat{c}_{opt}=- \frac{\text{Cov}(\hat{E}_{f},\hat{E}_{g})}{\text{Var}(\hat{E}_{g})}
$$
and
$$
\text{Var}(\hat{E}^{ \hat{c}_{opt}}_{f})=\text{Var}(\hat{E}_{f})-\frac{\text{Cov}(\hat{E}_{f},\hat{E}_{g})^{2}}{\text{Var}(\hat{E}_{g})}
$$
therefore, the stronger the covariance between the two estimates, the greater the reduction in Monte Carlo error.