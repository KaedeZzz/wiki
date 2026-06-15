---
source: "KaedeSync/_Knowledge/Mathematics/Probability Theory/Basics/Distributions/Exponential Density.md"
ingested: 2026-06-09
---

Characterise “the distribution of the time/distance between two successive succcesses”
$$
X\sim \text{Exp}(\lambda)\Leftrightarrow f_X(x)=\begin{cases}\lambda e^{-\lambda x}\text{ if } x\ge 0,\\0\text{ otherwise.}\end{cases}\quad\text{with }\lambda \in \mathbb{R^+}
$$

See: [[Poisson Distribution]]

*Consider $X_t=\text{Pois}(\lambda t)$.*
*In time interval $t$ from the beginning, the possibility that nothing happened = $P_{X_t}(0)=e^{-\lambda t}$*
*Thus, let $T$ denote the time of next occurrence, $P(T>t)=e^{-\lambda t}$*
*$F_T(t)=P(0<T\le t)=1-e^{-\lambda t}$*
*$f_T(t)=\frac{d}{dt}F_T(t)=\lambda e^{-\lambda t}$*

Expectation: $\mathbb E[X]=1/\lambda$
Variance: $\text{Var}[X]=1/\lambda^2$
Mode: $x_{\max}=0$
Median: $Q_{1/2}=(\ln2)/\lambda$
Skewness: $2>0$ → strongly right-tailed