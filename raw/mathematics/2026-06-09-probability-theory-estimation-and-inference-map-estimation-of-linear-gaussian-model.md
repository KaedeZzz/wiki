---
source: "KaedeSync/_Knowledge/Mathematics/Probability Theory/Estimation and Inference/MAP Estimation of Linear Gaussian Model.md"
ingested: 2026-06-09
---

Suppose the prior on parameter vector $\mathbf{\theta}$ is a [[Multivariate Gaussian]]:
$$
p(\mathbf{\theta})=\mathcal N(\mathbf{m}_{\mathbf{\theta}},\mathbf{C}_{\mathbf{\theta}})=\frac{1}{(2\pi)^{P/2}|\mathbf{C}_{\mathbf{\theta}}|^{1/2}}\exp\left( -\frac{1}{2}(\mathbf{\theta}-\mathbf{m}_{\mathbf{\theta}})^{T} \mathbf{C}_{\mathbf{\theta}}^{-1}(\mathbf{\theta}-\mathbf{m}_{\mathbf{\theta}})\right)
$$
where $\mathbf{m}_{\mathbf{\theta}}$ is the prior parameter mean vector and $\mathbf{C_{\theta}}$ is the prior parameter covariance matrix.

The posterior distribution:
$$
\begin{align}
p(\mathbf{\theta}|\mathbf{x}) & \propto p(\mathbf{x}|\mathbf{\theta})p(\mathbf{\theta}) \\
 & \propto\frac{1}{(2\pi)^{P/2}|\mathbf{C}_{\mathbf{\theta}}|^{1/2}}\exp\left( -\frac{1}{2}(\mathbf{\theta}-\mathbf{m}_{\mathbf{\theta}})^{T} \mathbf{C}_{\mathbf{\theta}}^{-1}(\mathbf{\theta}-\mathbf{m}_{\mathbf{\theta}})\right) \frac{1}{(2\pi\sigma_{e}^{2})^{N/2}}\exp\left( -\frac{1}{2\sigma_{e}^{2}}(\mathbf{x}-\mathbf{G\theta})^{T}(\mathbf{x}-\mathbf{G\theta}) \right) \\
 
\end{align}
$$
log of posterior:
$$
-2 \log p(\mathbf{\theta}|\mathbf{x})=(\mathbf{\theta}-\mathbf{m_{\theta}})^{T}\mathbf{C_{\theta}}^{-1}(\mathbf{\theta}-\mathbf{m_{\theta}})+\frac{1}{\sigma_{e}^{2}}(\mathbf{x}-\mathbf{G\theta})^{T}(\mathbf{x}-\mathbf{G\theta})
$$
Following a similar approach to differentiate with respect to $\mathbf{\theta}$ and set to $0$:
$$
\mathbf{\theta}^{MAP}=(\mathbf{G}^{T}\mathbf{G}+\sigma_{e}^{2}\mathbf{C_{\theta}}^{-1})^{-1}(\mathbf{G}^{T}\mathbf{x}+\sigma_{e}^{2}\mathbf{C_{\theta}}^{-1}\mathbf{m_{\theta}})
$$

From the expression we can find that, the more "diffuse" the higher the magnitude of diagonal elements of $\mathbf{C_{\theta}}$ is (both absolutely and in comparison with off-diagonal elements), the **less prior information** we impose on the estimate.

In the limit the prior tends to a uniform (‘flat’) prior with all $\mathbf{\theta}$ equally probable; In this limit $\mathbf{C_{\theta}}^{-1}=0$ and the estimate is identical to the [[ML Estimation of Linear Gaussian Model]]. This demonstrates that the ML estimate can be interpreted as an MAP estimate with uniform prior.

The MAP estimate will also tend towards ML estimate when the likelihood is strongly ‘peaked’ around its maximum compared with the prior; in this case the prior has little influence on the posterior. It is known that as $N\to \infty$ the Bayesian solution tends towards ML solution.

Why this characteristics of $\mathbf{C_\theta}$ is a sign of "diffuse" prior? #SUPO 