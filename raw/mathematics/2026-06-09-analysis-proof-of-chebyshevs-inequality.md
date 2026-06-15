---
source: "KaedeSync/_Knowledge/Mathematics/Analysis/Proof of Chebyshev's Inequality.md"
ingested: 2026-06-09
---

Note that 
$$
P(|X-\mathbb{E}\{X\}|\geq a)\Leftrightarrow P(|X-\mathbb{E}\{X\}|^{2}\geq a^{2})
$$
Then, let $Y=|X-\mathbb{E}\{X\}|^{2}$. Since $Y$ is non-negative, apply [[Markov's Inequality]]:
$$
P(Y\geq a^{2})\leq \frac{\mathbb{E}\{Y\}}{a^{2}}\implies P(|X-\mathbb{E}\{X\}|\geq a)\leq \frac{\text{Var}[X]}{a^{2}}
$$

[[Chebyshev's Inequality]]