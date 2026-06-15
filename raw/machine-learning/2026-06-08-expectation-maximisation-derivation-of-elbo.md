---
source: KaedeSync/_Knowledge/Machine Learning/Expectation-Maximisation/Derivation of ELBO.md
ingested: 2026-06-08
---

Define $x_{i}$ as the observation of the $i$-th state and $z_{i}$ the latent state $i$.
Firstly we pick any **prior** distribution $q(Z)$ over the latent variables (*usually convenient to factorise as $q(Z)=\prod_{i}q_{i}(z_{i})$*) such that the log likelihood of observation $x_{i}$ can be expressed as:
$$
\log p(x_{i}|\theta)= \sum_{z_{i}}\log p(x_{i},z_{i}|\theta)
$$
where, given value of discrete latent state $z_{i}$, the distribution of observation $x_{i}$ is a marginalisation of the joint distribution.

We look into the **lower boundary** of the log-likelihood by using Jensen's inequality:

![[Jensen's Inequality]]

$$
\sum_{z_{i}}\log p(x_{i},z_{i}|\theta)=\sum_{z_{i}}\log \left(q_{i}(z_{i}) \frac{p(x_{i},z_{i}|\theta)}{q_{i}(z_{i})}\right)\geq \sum_{z_{i}}q_{i}(z_{i})\log\frac{p(x_{i},z_{i}|\theta)}{q_{i}(z_{i})}
$$
as the $\log$ function is convex.
Now, we sum over each ob the observations:
$$
\mathcal{L}(\theta)=\sum_{i=1}^{N}\log p(x_{i}|\theta)\geq \sum_{i=1}^{N}\sum _{z_{i}}q_{i}(z_{i})\log\frac{p(x_{i},z_{i}|\theta)}{q_{i}(z_{i})}
$$
where the latter can be formally defined as
$$
\mathcal{F}(q,\theta)=\sum_{i=1}^{N}\sum _{z_{i}}q_{i}(z_{i})\log\frac{p(x_{i},z_{i}|\theta)}{q_{i}(z_{i})}=\sum_{i=1}^{N}\mathbb{E}_{q_{i}}\left[ \log \frac{p(x_{i},z_{i}|\theta)}{q_{i}(z_{i})} \right]
$$
as the [[Evidence Lower Bound (ELBO)]], where
$$
\mathcal{L}(\theta)\geq \mathcal{F}(q,\theta)
$$

We break the expression into two parts:
$$
\begin{align}
\mathcal{F}(q,\theta) & =\sum_{i=1}^{N}\mathbb{E}_{q_{i}}[\log p(x_{i},z_{i}|\theta)]-\sum_{i=1}^{N}\mathbb{E}_{q_{i}}[\log q_{i}(z_{i})] \\
 & =\sum_{i=1}^{N}\mathbb{E}_{q_{i}}[\log p(x_{i},z_{i}|\theta)]+H(q)
\end{align}
$$
where
$$
H(q)=\sum_{i}\sum_{z_{i}}q_{i}(z_{i})\log q_{i}(z_{i})
$$
**KL Divergence Equation**
Notice that
$$
\begin{align}
\mathcal{F}_{i}(q_{i},\theta) & =\sum_{z_{i}}q_{i}(z_{i})\log \frac{{p(x_{i},z_{i}|\theta)}}{q_{i}(z_{i})} \\
 & =\sum_{z_{i}}q_{i}(z_{i})\log p(x_{i}|\theta)+\sum_{z_{i}}q_{i}(z_{i})\log \frac{p(z_{i}|x_{i},\theta)}{q_{i}(z_{i})} \\
 & =\log p(x_{i}|\theta)-KL
(q_{i}||p(z_{i}|x_{i},\theta))\end{align}
$$

summing over all observations,
$$
\mathcal{L}(\theta)=\mathcal{F}(q,\theta)+\sum_{i}KL(q_{i}||p(z_{i}|x_{i},\theta))
$$

