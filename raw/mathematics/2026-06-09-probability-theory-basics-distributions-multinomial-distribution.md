---
source: "KaedeSync/_Knowledge/Mathematics/Probability Theory/Basics/Distributions/Multinomial Distribution.md"
ingested: 2026-06-09
---

Consider a discrete random variable $X$ that can take one of $m$ values $x_{1},\dots,x_{m}$. Out of $n$ independent trials, let $k_{i}$ be the number of times $X=x_{i}$ is observed. It follows that $\sum_{i=1}^{m}k_{i}=n$. 
Denote by the probability that $X=x_{i}$ such that $\sum_{i=1}^{m}\pi_{i}=1$.

The probability of observing a vector of occurrences $\mathbf{k}$ is given by the  multinomial distribution parametrised by $\pi$: 
$$
p(\mathbf{k}|\pi, n)=\frac{n!}{k_{1}!k_{2}!\dots k_{m}!}\prod_{i=1}\pi_{i}^{k_{i}}
$$
