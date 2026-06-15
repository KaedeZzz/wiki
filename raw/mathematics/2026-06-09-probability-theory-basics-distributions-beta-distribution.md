---
source: "KaedeSync/_Knowledge/Mathematics/Probability Theory/Basics/Distributions/Beta Distribution.md"
ingested: 2026-06-09
---

$$
\text{Beta}(\pi|\alpha,\beta)=\frac{\Gamma(\alpha+\beta)}{\Gamma(\alpha)\Gamma(\beta)}\pi^{\alpha-1}(1-\pi)^{\beta-1}
$$
where $\alpha$ and $\beta$ are shape parameters. 

![[Gamma Function]]

We can think of parameters $\alpha$ and $\beta$ as prior counts: $\alpha-1$ represents the number of observed successes, and $\beta-1$ represents the number of observed failures. In this way, the beta distribution describes the *belief about a probability* after seeing $\alpha-1$ successes and $\beta-1$ defeats.