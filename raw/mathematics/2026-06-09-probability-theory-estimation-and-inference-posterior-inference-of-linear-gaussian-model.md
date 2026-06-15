---
source: "KaedeSync/_Knowledge/Mathematics/Probability Theory/Estimation and Inference/Posterior Inference of Linear Gaussian Model.md"
ingested: 2026-06-09
---

Instead of optimal estimate, we examine the whole posterior distribution of [[MAP Estimation of Linear Gaussian Model]].
$$
\mathbf{\theta}^{MAP}=(\mathbf{G}^{T}\mathbf{G}+\sigma_{e}^{2}\mathbf{C_{\theta}}^{-1})^{-1}(\mathbf{G}^{T}\mathbf{x}+\sigma_{e}^{2}\mathbf{C_{\theta}}^{-1}\mathbf{m_{\theta}})
$$

Define terms:
$$
\begin{align}
\mathbf{\Phi} & =\mathbf{G}^{T}\mathbf{G}+\sigma_{e}^{2}\mathbf{C}_{\mathbf{\theta}}^{-1} \\
 \mathbf{\Theta}& =\mathbf{G}^{T}\mathbf{x}+\sigma_{e}^{2}\mathbf{C}_{\mathbf{\theta}}^{-1}\mathbf{m_{\theta}}
\end{align}
$$
so
$$
\mathbf{\theta}^{MAP}=\mathbf{\Phi}^{-1}\mathbf{\Theta}
$$
Therefore, the log-posterior function:
$$
\begin{align}
 & \frac{1}{\sigma_{e} ^{2}}(\mathbf{x}-\mathbf{G\theta})^{T}(\mathbf{x}-\mathbf{G\theta})+(\mathbf{\theta}-\mathbf{m_{\theta}})^{T}\mathbf{C_{\theta}}^{-1}(\mathbf{\theta}-\mathbf{m_{\theta}}) \\
 & =\frac{1}{\sigma_{e} ^{2}}((\mathbf{\theta}-\mathbf{\theta}^{MAP})^{T}\mathbf{\Phi}(\mathbf{\theta}-\mathbf{\theta}^{MAP})+\mathbf{x}^{T}\mathbf{x}+\sigma_{e}^{2}\mathbf{m_{\theta}}^{T}\mathbf{C_{\theta}}^{-1}\mathbf{m_{\theta}}-\mathbf{\Theta}^{T}\mathbf{\theta}^{MAP})
\end{align}
$$
Notice that, the first term is exactly in the form of [[Multivariate Gaussian]] with
$$
\mathbf{m}_{\theta}^{\text{post}}=\mathbf{\theta}^{MAP},\quad \mathbf{C}_{\theta}^{\text{post}}=\sigma_{e}^{2}\mathbf{\Phi}^{-1}
$$
and none other terms are dependent on $\mathbf{\theta}$; hence, we can conclude that the posterior distribution is itself a multivariate Gaussian
$$
p(\mathbf{\theta}|\mathbf{x})=\mathcal N(\mathbf{\theta}^{MAP},\sigma_{e}^{2}\mathbf{\Phi}^{-1})
$$
