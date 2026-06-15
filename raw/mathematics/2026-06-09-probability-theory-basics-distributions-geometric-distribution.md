---
source: "KaedeSync/_Knowledge/Mathematics/Probability Theory/Basics/Distributions/Geometric Distribution.md"
ingested: 2026-06-09
---

"How many Bernoulli trials needed for first success"
$$
X\sim \text{Geo}(p)\Leftrightarrow P_X(k)=\begin{cases}p(1-p)^{k-1} \text{ if }k\in \mathbb N^+,\\0\text{ otherwise.}\end{cases}\quad\text{with }p \in[0, 1]
$$
The support is discrete finite.
Expectation: $\mathbb{E}[X]=1/p$
Variance: $Var[X]={1-p} / {p ^{2} }$
Entropy: $\mathbb{H}[X]=\mathcal H_{2}(p) /p$
