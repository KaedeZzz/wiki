---
source: "KaedeSync/_Knowledge/Mathematics/Probability Theory/Estimation and Inference/Estimators/OLS Estimator of General Linear Model.md"
ingested: 2026-06-09
---

We derive the **Ordinary Least Squares** estimator to estimate parameter $\theta$ of the [[General Linear Model (GLM)]].

We attempt to find the 'best fit' model by minimising the error $J=\mathbf{e}^{T}\mathbf{e}$.
Expand with $\mathbf{e}=\mathbf{x}-\mathbf{G\theta}$:
$$
\begin{align}
J & =(\mathbf{x}-\mathbf{G\theta})^{T}(\mathbf{x}-\mathbf{G\theta}) \\
 & =\mathbf{x}^{T}\mathbf{x}+\mathbf{\theta}^{T}\mathbf{G}^{T}\mathbf{G\theta}-2\mathbf{\theta}^{T}\mathbf{G}^{T}\mathbf{x}
\end{align}
$$
Now, define the vector gradient:

![[Vector Gradient]]

We obtain:
$$
\frac{dJ}{d\mathbf{\theta}}=2\mathbf{G}^{T}\mathbf{G\theta}-2\mathbf{G}^{T}\mathbf{x}
$$
at a stationary point, set $\frac{dJ}{d\mathbf{\theta}}=\vec{0}$:
$$
\begin{align}
\mathbf{G}^{T}\mathbf{G\theta} & =\mathbf{G}^{T}\mathbf{x} \\
\mathbf{\theta}^{OLS} & =(\mathbf{G}^{T}\mathbf{G})^{-1}\mathbf{G}^{T}\mathbf{x}
\end{align}
$$
