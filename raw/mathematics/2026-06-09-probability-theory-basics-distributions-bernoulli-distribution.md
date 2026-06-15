---
source: "KaedeSync/_Knowledge/Mathematics/Probability Theory/Basics/Distributions/Bernoulli Distribution.md"
ingested: 2026-06-09
---

"Coin toss"
$$
X\sim \text{Ber}(p)\Leftrightarrow P_X(x)=\begin{cases}p \text{ if }x=1,\\1-p \text{ if }x=0\\0\text{ otherwise.}\end{cases}\quad\text{with }p \in[0, 1]
$$
The support is discrete finite.
Expectation: $\mathbb E[X]=p$
Variance: $\text{Var}[X]=p(1-p)$
Entropy: $\mathbb H[X]=\mathcal H_2(p)=-p\log_2p-(1-p)\log_2(1-p)$
