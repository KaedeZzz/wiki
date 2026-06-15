---
source: KaedeSync/_Knowledge/Machine Learning/Expectation-Maximisation/EM Algorthm on Gaussian Mixture Model.md
ingested: 2026-06-08
---

Given that the data likelihood for one sample is:
$$
p(x_{n},z_{n}=k|\theta)=\pi_{k}\mathcal{N}(x_{n}|\mu_{k},\Sigma_{k})
$$
where $z_{n}$ is the latent variable indicating the Gaussian component the data point is in, $\pi_{k}$ the prior of latent variable. 

**E-step**
We compute the posterior of each parameter.
$$
p(z_{n}=k|x_{n},\theta^{(t)})=\frac{{\pi_{k}\mathcal{N}(x_{n}|\mu_{k},\Sigma_{k})}}{\sum_{k}\pi_{k}\mathcal{N}(x_{n}|\mu_{k},\Sigma_{k})}=\gamma_{nk}
$$
where $\gamma_{nk}$ represents the "soft count" of how much of data point $x_{n}$ is explained by component $k$.

**Auxiliary function**
$$
\begin{align}
Q(\theta,\theta^{(t)}) & =\sum_{n=1}^{N}\sum_{k=1}^{K}p(z_{n}=k|x_{n},\theta^{(t)})\log(x_{n},z_{n}=k|\theta^{(t)}) \\
 & =\sum_{n=1}^{N}\sum_{k=1}^{K}\gamma_{nk}\log(\pi_{k}\mathcal{N}(x_{n}|\mu_{k},\Sigma_{k})) \\
 & =\sum_{n=1}^{N}\sum_{k=1}^{K}\gamma_{nk}(\log\pi_{k}+\log\mathcal{N}(x_{n}|\mu_{k},\Sigma_{k}))
\end{align}
$$
[[Auxiliary Function]] will be maximised subject to $\sum_{k}\pi_{k}=1$.

**M-step for $\pi_{k}$**
We can look only on part of $Q$ that is relevant to $\pi$:
$$
Q_{\pi}=\sum_{n=1}^{N}\sum_{k=1}^{K}\gamma_{nk}\log \pi_{k}=\sum_{k=1}^{K}N_{k}\log \pi_{k}\quad
$$
where $N_{k}=\sum_{n}\gamma_{nk}$ represents the total "soft count" of component $k$.
Since the optimisation is subject to the constrain of $\sum_{k}\pi_{k}=1$, we add a [[Lagrange Multiplier]]:
$$
\mathcal{L}=\sum_{k}N_{k}\log \pi_{k}+\lambda\left( 1-\sum_{k}\pi_{k} \right)
$$
derivative with respect to $\pi_{k}$:
$$
\frac{{\partial \mathcal{L}}}{\partial \pi_{k}}=\frac{N_{k}}{\pi_{k}}-\lambda=0\implies \pi_{k}=\frac{N_{k}}{\lambda}
$$
impose constraint:
$$
\sum_{k}\pi_{k}=\sum_{k} \frac{N_{k}}{\lambda}=1\implies\lambda=N\implies \pi_{k}=\frac{N_{k}}{N}
$$
which is very naively saying that the prior of a component equals to *the proportion of its soft count.*

**M-step for $\mu_{k}$**
Inspect the log-Gaussian term in auxiliary function:

![[Log of Multivariate Gaussian]]

Notice that only the quadratic term is relevant to $\mu$, so:
$$
Q_{\mu}=\sum_{n}\sum_{k}\gamma_{nk}\left( -\frac{1}{2}(x_{n}-\mu_{k})^{T}\Sigma_{k}^{-1}(x_{n}-\mu_{k}) \right)
$$
derivative:
$$
\frac{{\partial Q_{\mu}}}{\partial \mu_{k}}=\sum_{n}\gamma_{nk}(-\Sigma_{k}^{-1}(x_{n}-\mu_{k}))=-\sum_{n}\gamma_{nk}\Sigma_{k}^{-1}(x_{n}-\mu_{k})=0
$$
which leads to
$$
\begin{align}
-\Sigma_{k}^{-1}\sum_{n}\gamma_{nk}(x_{n}-\mu_{k})=0\implies \mu_{k}\sum_{n}\gamma_{nk}=\sum_{n}\gamma_{nk}x_{n}\implies \mu_{k}=\frac{\sum_{n}\gamma_{nk}x_{n}}{N_{k}}
\end{align}
$$
which is *a weighted mean of all datapoints that includes the component.*

**M-step for $\Sigma_{k}$**
Following a similar approach,
$$
Q_{\Sigma}=-\frac{1}{2}\sum_{n=1}^{N}\gamma_{nk}(\log \lvert \Sigma_{k} \rvert +(x_{n}-\mu_{k})^{T}\Sigma_{k}^{-1}(x_{n}-\mu_{k}))
$$
Calculus identities:
$$
\begin{align}
\frac{{\partial \log \lvert \Sigma \rvert }}{\partial \Sigma} & =(\Sigma^{-1})^{T}=\Sigma^{-1} \\
\frac{{\partial ((x-\mu)^{T}\Sigma^{-1}(x-\mu))}}{\partial \Sigma} & =-\Sigma^{-1}(x-\mu)(x-\mu)^{T}\Sigma^{-1}
\end{align}
$$
putting into the expression and set derivative to zero,
$$
0=-\frac{1}{2}\sum_{n}\gamma_{nk}(\Sigma_{k}^{-1}-\Sigma_{k}^{-1}(x_{n}-\mu_{k})(x_{n}-\mu_{k})^{T}\Sigma_{k}^{-1})
$$
left multiply the equation by $-2\Sigma_{k}$ and right multiply by $\Sigma_{k}$:
$$
\sum_{n}\gamma_{nk}((x_{n}-\mu_{k})(x_{n}-\mu_{k})^{T}-\Sigma_{k})=0
$$
so
$$
\Sigma_{k}=\frac{1}{N_{k}}\sum_{n=1}^{N}\gamma_{nk}(x_{n}-\mu_{k})(x_{n}-\mu_{k})^{T}
$$
which is a *a weighted covariance of all datapoints that includes the component.*
