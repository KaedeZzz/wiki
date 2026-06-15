---
source: "KaedeSync/_Knowledge/Mathematics/Probability Theory/Estimation and Inference/Posterior Distribution.md"
ingested: 2026-06-09
---

Estimation of random parameters $\mathbf{\theta}$ from a random vector $\mathbf{x}$ of observations:
$$
p(\mathbf{\theta}|\mathbf{x})=\frac{{p(\mathbf{x}|\mathbf{\theta})p(\mathbf{\theta})}}{p(\mathbf{x})}
$$
where $p(\mathbf{\theta})$ is the **prior** for the parameters.

The generation of the posterior distribution can be thought of as a **refinement** to any previous ('prior') **knowledge** about the parameters.
- If we start off with little information about $\mathbf{\theta}$, then the posterior obtains information almost **solely** from $\mathbf{x}$. 
- Conversely, if $p(\mathbf{\theta})$ expresses a significant amount of information about $\mathbf{\theta}$, then $\mathbf{x}$ will contribute relatively less new information to the posterior.

The denominator $p(\mathbf{x})$, referred to as the **marginal likelihood**, is constant for any given observation x; thus it may be ignored if we are only interested in the **relative** posterior probabilities of different parameters. Hence, the [[Bayes Theorem]] is often stated as:
$$
p(\mathbf{\theta}|\mathbf{x})\propto p(\mathbf{x}|\mathbf{\theta})p(\mathbf{\theta})
$$
and $p(\mathbf{x})$ may be calculated from marginal integration:
$$
p(\mathbf{x})=\int p(\mathbf{x}|\mathbf{\theta})p(\mathbf{\theta})d\mathbf{\theta}
$$
which serves as a normalisation constant for the posterior.