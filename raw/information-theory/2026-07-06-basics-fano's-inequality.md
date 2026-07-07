---
source: KaedeSync/_Knowledge/Information Theory/Basics/Fano's Inequality.md
ingested: 2026-07-06
---

Scenario/mechanism:
$$
X\to P_{Y|X}\to Y\to\text{Estimator}\to \hat{X}=g(Y)
$$
- We want to estimate $X$ by observing a correlated random variable $Y$.
- The *probability of error* of an estimator $\hat{X}=g(Y)$ is $P_{e}=Pr(\hat{X}\neq X)$.
- Given that the random variable $X$ takes values in the set $\mathcal X$, we wish to find an inequality relationship that describes the bound(s) of $P_{e}$.

For any estimator $\hat{ X}$ such that $X-Y-\hat{X}$, the probability of error satisfies
$$
1+P_{e}\log|\mathcal X|\geq H(X|\hat{X})\geq H(X|Y)
$$
in other words,
$$
P_{e}\geq \frac{H(X|Y)-1}{\log|\mathcal X|}
$$
this bound on $P_{e}$ is known as *Fano's Inequality*.

[[Information Theory]], [[The Data Processing Inequality]]

