---
source: KaedeSync/_Knowledge/Machine Learning/Gaussian Process/Posterior Gaussian Process.md
ingested: 2026-06-08
---

The [[Gaussian Process]] will be used as a prior for Bayesian inference. Therefore, how to update this prior with training data?

Let $\mathbf{f}$ be the known training cases and $\mathbf{f}^{*}$ be the set of function values corresponding to test set inputs. The joint distribution is then:
$$
\begin{bmatrix}
\mathbf{f} \\
\mathbf{f}^{*}
\end{bmatrix}
\sim \mathcal{N}(\begin{bmatrix}
\mu \\
\mu_{*}
\end{bmatrix},
\begin{bmatrix}
\Sigma & \Sigma_{*} \\
\Sigma_{*}^{T} & \Sigma_{**}
\end{bmatrix})
$$
we know that the conditional distribution of a multivariate Gaussian is still a Gaussian, and that applies to this joint distribution, where the conditional of $\mathbf{f}_{*}$ given $\mathbf{f}$ can be viewed as a predictive distribution:
$$
\mathbf{f}_{*}|\mathbf{f}\sim \mathcal{N}(
\mu_{*}+\Sigma_{*}^{T}\Sigma^{-1}(\mathbf{f}-\mathbf{\mu}),\Sigma_{**}-\Sigma_{*}^{T}\Sigma^{-1}\Sigma_{*}
)
$$
the corresponding vectorized **posterior process** is:
$$
\begin{align}
f|\mathcal{D} & \sim \mathcal{GP}(m_{\mathcal{D}},k_{\mathcal{D}}) \\
m_{\mathcal{D}}(x)  & =m(x)+\Sigma(X,x)\Sigma^{-1}(\mathbf{f}-\mathbf{m}) \\
k_{\mathcal{D}}(x,x') & =k(x,x')-\Sigma(X,x)^{T}\Sigma^{-1}\Sigma(X,x')
\end{align}
$$
where $\Sigma(X,x)$ is a vector of covariances between every training case and $x$. 

In this case, function values $\mathbf{f}_{*}$ can be sampled from the joint posterior distribution by evaluating mean and covariance matrix and generate samples accordingly.

Note that the posterior variance is always smaller than the prior variance, since the data has given some additional information.