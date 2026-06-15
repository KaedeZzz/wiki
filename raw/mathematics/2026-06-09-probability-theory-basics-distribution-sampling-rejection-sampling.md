---
source: "KaedeSync/_Knowledge/Mathematics/Probability Theory/Basics/Distribution Sampling/Rejection Sampling.md"
ingested: 2026-06-09
---

To sample from distribution $h(x)$, assume we can sample from distribution with pdf $g(x)$, and there exists a constant such that $g(x)> \frac{h(x)}{M}$ for all $x$, then:
1. Sample $U\sim\text{Uniform}(0,1)$ and $X$ from $g$
2. If $U\leq \frac{h(x)}{Mg(x)}$ return $X$, else return to step 1.

*Proof:*
$$
\begin{align}
P\left( U\leq \frac{h(x)}{Mg(x)},X\leq x \right)&=\int_{-\infty}^{x}dx'\int_{0}^{\frac{h(x')}{Mg(x')}}du\ f_{U,X}(u,x') \\
&=\int_{-\infty}^{x}dx'\int_{0}^{\frac{h(x')}{Mg(x')}}du\ f_{X}(x') \\
&=\int_{-\infty}^{x}dx'\int_{0}^{\frac{h(x')}{Mg(x')}}du\ g(x') \\
&=\int_{-\infty}^{x}dx'\frac{h(x')}{Mg(x')}g(x') \\
&=\frac{H(x)}{M}
\end{align}
$$
Then:
$$
P\left( U\leq \frac{h(x)}{Mg(x)} \right)=\lim_{ x \to \infty } \frac{H(x)}{M}=\frac{1}{M}
$$
 
 Therefore, consider conditional probability:
$$
P\left( X\leq x\ |\ U\leq \frac{h(x)}{Mg(x)} \right)= \frac{{H(x) / M}}{1 / M}=H(x)
$$

Thus $x$ is sampled from $h(x)$.