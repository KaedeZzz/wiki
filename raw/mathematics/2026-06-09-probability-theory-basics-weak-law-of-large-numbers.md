---
source: "KaedeSync/_Knowledge/Mathematics/Probability Theory/Basics/Weak Law of Large Numbers.md"
ingested: 2026-06-09
---

Let $X_{1},X_{2},\dots$ be a sequence of i.i.d. [[Random Variable]] with finite mean $\mu$. Let $S_{n}= \frac{1}{n}\sum_{i=1}^{n}X_{i}$. For any $\epsilon>0$,
$$
\lim_{ n \to \infty } P(|S_{n}-\mu|\geq\epsilon)=0
$$
*For large enough number of i.i.d. random variables, their average will be **arbitrarily** close to mean of one variable.*
Proof: from [[Chebyshev's Inequality]],
$$
\sum_{n} P(|S_{n}-\mu|\geq\epsilon)\leq \frac{\sigma ^{2}}{n \epsilon ^{2}}
$$
which will tend to $0$ as $n\to \infty$.

WLLN is an example of convergence in probability of a sequence of random variables.

[[Probability and Statistics]]