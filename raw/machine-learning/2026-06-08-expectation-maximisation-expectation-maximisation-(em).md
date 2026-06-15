---
source: KaedeSync/_Knowledge/Machine Learning/Expectation-Maximisation/Expectation Maximisation (EM).md
ingested: 2026-06-08
---

Expectation-maximisation algorithm iteratively **guess the hidden state structure** and **updates model parameters** to better explain the data.
- Estimate hidden-variable posteriors using current parameters;  i. (**E-step**)
- Re-estimate parameters as if the latent distribution were known; *refit model using hidden causes*.(**M-step**)

In this process, each iteration is guaranteed not to decrease the likelihood of observations.

EM attempts to replace hard assignments of label with soft probability-based assignments.

According to [[Evidence Lower Bound (ELBO)]]:
$$
\mathcal{L}(\theta)=\mathcal{F}(q,\theta)+\sum_{i}KL(q_{i}||p(z_{i}|x_{i},\theta))
$$
**E-step**
Compute the posterior distribution over hidden variables using the **old parameters**.
Match our proposal of latent distribution, $q(Z)$, with the posterior latent distribution:
$$
q_{i}^{(t+1)}(z_{i})=p(z_{i}|x_{i},\theta^{(t)})
$$
in this case the [[KL Divergence]] term diminish and
$$
\mathcal{L}(\theta^{(t)})=\mathcal{F}(q^{(t+1)},\theta^{(t)})
$$

**M-step**
Now we attempt to optimise $\theta$ by doing [[Maximum Likelihood Estimation]], i.e. maximise the likelihood. ***Since we do not know the expression of likelihood, instead, we optimise the ELBO***:
$$
\begin{align}
\hat{\theta} & =\arg\max_{\theta}\mathcal{F}(q^{(t+1)},\theta)  \\
 & =\arg\max_{\theta}\mathcal{F}(p(z|x,\theta^{(t)}),\theta) \\
& =\arg\max_{\theta}\left[\sum_{i=1}^{N}\mathbb{E}_{q_{i}\sim p(z_{i}|x_{i},\theta^{(t)})}[\log p(x_{i},z_{i}|\theta)]+H(q)\right] \\
&=\arg\max_{\theta}\sum_{i=1}^{N}\mathbb{E}_{p(z_{i}|x_{i},\theta^{(t)})}[\log p(x_{i},z_{i}|\theta)] \\
 & =\arg\max_{\theta}\sum_{i=1}^{N}\sum_{z_{i}}p(z_{i}|x_{i},\theta^{(t)})\log p(x_{i},z_{i}|\theta) \\
 & =\arg\max_{\theta}Q(\theta,\theta^{(t)})
\end{align}
$$
where
$$
Q(\theta,\theta^{(t)})=\sum_{i=1}^{N}\sum_{z_{i}}p(z_{i}|x_{i},\theta)\log p(x_{i},z_{i}|\theta)
$$
is defined as the [[Auxiliary Function]].

Notice that:
$$
\mathcal{L}(\theta^{(t+1)})\geq \mathcal{F}(q^{(t+1)},\theta^{(t+1)})\geq \mathcal{F}(q^{(t+1)},\theta)=\mathcal{L}(\theta^{(t)})
$$
so that the optimisation is guaranteed to converge to a local minima.