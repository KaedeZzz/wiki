---
source: KaedeSync/_Knowledge/Machine Learning/Expectation-Maximisation/Evidence Lower Bound (ELBO).md
ingested: 2026-06-08
---

Also known as **free energy** for [[Expectation Maximisation (EM)]].

For a [[Latent Variable]] model, the log-likelihood of a datum is:
$$
\log p(x|\theta)=\log \sum_{z}p(x,z|\theta)
$$
multiply and divide by some distribution $q(z)$:
$$
\log p(x|\theta)=\log \sum_{z}q(z) \frac{p(x,z|\theta)}{q(z)}=\log \mathbb{E}_{q}\left[ \frac{p(x,z|\theta)}{q(z)} \right]
$$
Since the $\log$ function is concave, [[Jensen's Inequality]] gives
$$
\log \mathbb{E}_{q}[f(z)]\geq \mathbb{E}_{q}[\log f(z)]
$$
So
$$
\log p(x|\theta)\geq \sum_{z}q(z)\log \frac{p(x,z|\theta)}{q(z)}
$$
Define the sum of right side for a dataset
$$
\mathcal{F}(q,\theta)=\sum_{i=1}^{N}\sum_{z_{i}}q_{i}(z_{i})\log \frac{p(x_{i},z_{i}|\theta)}{q_{i}(z_{i})}
$$
as the **evidence lower-bound**, which acts as the lower bound of the log-likelihood of the dataset, and is the *object maximised in EM*.

Furthermore, notice that:
$$
\log p(x|\theta)=\mathcal{F}(q,\theta)+\mathrm{KL}(q(z)||p(z|x,\theta))
$$
and the lower bound is reached when $q(z)$, the **proposal distribution**, is equal to the true posterior.