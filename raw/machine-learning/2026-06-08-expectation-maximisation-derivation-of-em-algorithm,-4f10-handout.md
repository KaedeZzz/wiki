---
source: KaedeSync/_Knowledge/Machine Learning/Expectation-Maximisation/Derivation of EM Algorithm, 4F10 Handout.md
ingested: 2026-06-08
---


[[Expectation Maximisation (EM)]] on [[Gaussian Mixture Model]].

Assuming the prior probability of component $k$ is $\lambda_{k}$, applying Jensen's inequality:
$$
\log\left(\sum_{m=1}^{M}\lambda_{m}p(\mathbf{x}|c_{m})\right)\geq \sum_{m=1}^{M}\lambda_{m}\log(p(\mathbf{x}|c_{m})),\quad s.t.\sum_{m=1}^{M}\lambda_{m}=1
$$
since the $\log$ function is convex.
Afterwards, we know that updating parameters from $\theta^{(k)}$ to $\theta^{(k+1)}$ desires
$$
\begin{align}
\mathcal{L}(\theta^{(k+1)})-\mathcal{L}(\theta^{(k)}) & =\sum_{i=1}^{N}\log\left(  \frac{p(\mathbf{x}_{i}|\theta^{(k+1)})}{p(\mathbf{x}_{i}|\theta^{(k)}} \right)\geq 0\text{ (as a constructive update)} \\
 & =\sum_{i=1}^{N}\log\left( \frac{1}{p(\mathbf{x}_{i}|\theta^{(k)})}\sum_{m=1}^{M}(p(\mathbf{x}_{i},c_{m}|\theta^{(k+1)})) \right) \\
 & =\sum_{i=1}^{N}\log\left( \frac{1}{p(\mathbf{x}_{i}|\theta^{(k)})}\sum_{m=1}^{M}\left( \frac{{P(c_{m}|\mathbf{x}_{i},\theta^{(k)})p(\mathbf{x}_{i},c_{m}|\theta^{(k+1)})}}{p(c_{m}|\mathbf{x}_{i},\theta^{(k+1)})} \right) \right) \\
 \text{(Jensen's Inequality) }& \geq \sum_{i=1}^{N}\sum_{m=1}^{M}P(c_{m}|\mathbf{x}_{i},\theta^{(k)})\log\left( \frac{p(\mathbf{x}_{i},c_{m}|\theta^{(k+1)})}{p(\mathbf{x}_{i}|\theta^{(k)})P(c_{m}|\mathbf{x}_{i},\theta_{k})} \right) \\
 & =\sum_{i=1}^{N}\sum_{m=1}^{M}P(c_{m}|\mathbf{x}_{i},\theta^{(k)})\log\left( \frac{p(\mathbf{x}_{i},c_{m}|\theta^{(k+1)})}{p(\mathbf{x}_{i},c_{m}|\theta^{(k)})} \right)  \\
 & =\mathcal{Q}(\theta^{(k)},\theta^{(k+1)})-\mathcal{Q}(\theta^{(k)},\theta^{(k)})
\end{align}
$$
where
$$
\mathcal{Q}(\theta^{(k)},\theta^{(k+1)})=\sum_{i=1}^{N}\sum_{m=1}^{M}P(c_{m}|\mathbf{x}_{i},\theta^{(k)})\log (p(\mathbf{x}_{i},c_{m}|\theta^{(k+1)}))
$$
is known as the *auxiliary function*.
Optimising the log-likelihood requires
$$
\mathcal{Q}(\theta^{(k)},\theta^{(k+1)})-\mathcal{Q}(\theta^{(k)},\theta^{(k)})\geq 0
$$
and its increase is a lower bound on the increase of log-likelihood.
*In expectation maximisation, we maximize auxiliary function rather than likelihood*; a nice thing is that it does not have the stability (oscillation) problem of the [[Learning Rate]] of [[Gradient Descent]] method.

**How to maximise auxiliary functions?**
because
$$
\log(p(\mathbf{x},c_{m}|\theta))=\log(p(\mathbf{x}|c_{m},\theta))+\log(P(c_{m}))=\log \mathcal{N}(\mathbf{x};\mu_{m},\mathbf{\Sigma}_{m})+\log(P(c_{m}))
$$
where $\mu_{j}$ is the mean of all items in a same label. Therefore,
$$
\begin{align}
\frac{\partial}{\partial \mu_{j}}\mathcal{Q}(\theta^{(k)},\theta) & =\frac{\partial}{\partial \mu_{j}}\sum_{i=1}^{N}\sum_{m=1}^{M}P(c_{m}|\mathbf{x}_{i},\theta^{(k)})\log (p(\mathbf{x}_{i},c_{m}|\theta)) \\
 & =\sum_{i=1}^{N}P(c_{j}|\mathbf{x}_{i}, \theta^{(k)}) \frac{\partial}{\partial \mu_{j}}\log(p(x_{i},c_{j}|\theta)) \\
 & =\sum_{i=1}^{N}P(c_{j}|\mathbf{x}_{i}, \theta^{(k)}) \frac{\partial}{\partial \mu_{j}}\log \mathcal{N}(\mathbf{x};\mu_{j},\mathbf{\Sigma}_{j})
\end{align}
$$

Generalising the discrete latent variable $c_{m}$ into continuous latent variable $\mathbf{z}$, we have a continuous form of auxiliary function:
$$
\mathcal{Q}(\theta^{(k)},\theta^{(k+1)})=\int p(\mathbf{z}|\mathbf{x},\theta^{(k)})\log(p(\mathbf{x},\mathbf{z}|\theta^{(k+1)}))d\mathbf{z}
$$
Therefore, we attempt to maximise auxiliary function rather than log-likelihood:
$$
\theta^{(k+1)}=\arg\max_{\theta}\{ \mathcal{Q}(\theta^{(k)},\theta) \}=\arg\max_{\theta}\left\{  \int p(\mathbf{z}|\mathbf{x},\theta^{(k)})\log(p(\mathbf{x},\mathbf{z}|\theta))d\mathbf{z}  \right\}
$$
How to estimate this property? A property of [[KL Divergence]] yields that
$$
\mathcal{KL}(p(\mathbf{x})||q(\mathbf{x}))=\int p(\mathbf{x})\log\left(  \frac{p(\mathbf{x})}{q(\mathbf{x})} \right)d\mathbf{x}=\mathbb{E}_{p}\left[ \log \frac{p(x)}{q(x)} \right]\geq 0
$$
Therefore, considering any valid distribution $q(\mathbf{z},\tilde{\theta})$, we have:
$$
\begin{align}
\mathcal{L }(\theta) & =\log(p(\mathbf{x}|\theta)) \\
 & =\int q(\mathbf{z},\tilde{\theta})\log(p(\mathbf{x}|\theta))d\mathbf{z} \\
 & =\int q(\mathbf{z},\tilde{\theta})\log\left( \frac{p(\mathbf{x}|\theta)p(\mathbf{z}|\mathbf{x},\theta)}{p(\mathbf{z}|\mathbf{x},\theta)} \right)d\mathbf{z} \\
 & =\mathbb{E}_{q(\mathbf{z},\tilde{\theta})}\left[ \frac{\log(p(\mathbf{x},\mathbf{z}|\theta))}{p(\mathbf{z}|\mathbf{x},\theta)} \right] \\
 & =\mathbb{E}_{q(\mathbf{z},\tilde{\theta})}\left[ \frac{\log(p(\mathbf{x},\mathbf{z}|\theta))}{q(\mathbf{z},\tilde{\theta})} \right] +\mathbb{E}_{q(\mathbf{z},\tilde{\theta})}\left[ \frac{\log(q(\mathbf{z},\tilde{\theta}))}{p(\mathbf{z}|\mathbf{x},\theta)} \right]  \\
 & \geq\mathbb{E}_{q(\mathbf{z},\tilde{\theta})}\left[ \frac{\log(p(\mathbf{x},\mathbf{z}|\theta))}{q(\mathbf{z},\tilde{\theta})} \right] =\mathcal{F}(q(\mathbf{z},\tilde{\theta}),\theta)
\end{align}
$$
with equality at $q(\mathbf{z},\tilde{\theta})=p(\mathbf{z}|\mathbf{x},\theta)$
