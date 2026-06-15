---
source: "KaedeSync/_Knowledge/Mathematics/Probability Theory/Basics/Distributions/Binomial Distribution.md"
ingested: 2026-06-09
---

"How many successes after $n$ trials"
$$
X\sim \text{B}(n,p)\Leftrightarrow P_X(k)=\begin{cases}{}^nC_kp^k(1-p)^{n-k} \text{ if }k\in \{0,1,\dots,n\},\\0\text{ otherwise.}\end{cases}\quad\text{with }p \in[0, 1]
$$
The support is discrete finite.
Expectation: $\mathbb{E}[X]=np$
Variance: $Var[X]=np(1-p)$
Entropy:
![[Stirling's Approximation]]
Thus,
$$
\mathbb H[X]\approx\log_2\sqrt{2\pi nep(1-p)}\text{ for }n\gg 1
$$
