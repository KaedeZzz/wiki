---
source: "KaedeSync/_Knowledge/Mathematics/Probability Theory/Estimation and Inference/Basics/Maximum Likelihood Estimation.md"
ingested: 2026-06-09
---

[[Estimation and Inference]]

![[Likelihood Function]]

The **Maximum Likelihood** estimate for parameter $\mathbf{\theta}$ is then the value of $\mathbf{\theta}$ that maximises the likelihood for given observations $\mathbf{x}$:
$$
\mathbf{\theta}^{\text{ML}}=\arg\max_{\theta}{ \{ f_{X|\Theta}(x|\theta) \} }
$$
The rationale is that the ML solution corresponds to the parameter vector which would have generated the observed data $x$ with highest probability.
Maximisation task is usually done by calculating differential.
