---
source: "KaedeSync/_Knowledge/Mathematics/Probability Theory/Basics/Distributions/Poisson Distribution.md"
ingested: 2026-06-09
---

Indicate “Number of occurrence after unit time”
$$
X\sim \text{Pois}(\lambda)\Leftrightarrow P_X(k)=\begin{cases}\lambda^ke^{-\lambda}/k! \text{ if }k\in \mathbb N,\\0\text{ otherwise.}\end{cases}\quad\text{with }\lambda \in \mathbb{R^+}
$$
The support is discrete infinite.
Expectation: $\mathbb E[X]=\lambda$
Variance: $\text{Var}[X]=\lambda$
Entropy: $\mathbb H[X]\approx\log_2\sqrt{2\pi e\lambda}\text{ for }n\gg 1$
