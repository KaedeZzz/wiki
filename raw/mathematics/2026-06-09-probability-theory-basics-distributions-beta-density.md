---
source: "KaedeSync/_Knowledge/Mathematics/Probability Theory/Basics/Distributions/Beta Density.md"
ingested: 2026-06-09
---

Characterise “What is the probability density of the Bernoulli parameter p given this observation?”
Using Bayes rule:

$$ f_{p|k}(p|k)=\frac{P_{k|p}(k|p)f_P(p)}{\int_0^1P_{k|p}(k|p)f_P(p)dp} $$

We believe that:
$P_{k|p}(k|p)={}^nC_kp^k(1-p)^{1-k}$
Prior to any observation, all values of $p$ are believed to be equally likely, i.e. $f_P(p)=1$

After some calculation we find:
$$
f_{p|k}(p|k)=\frac{(n+1)!}{k!(n-k)!}p^k(1-p)^{n-k}
$$

$$
X\sim\text{Beta}(\alpha, \beta)\Leftrightarrow f_X(x)=\begin{cases}\frac{\Gamma(\alpha+\beta)}{\Gamma(\alpha)\Gamma(\beta)}x^{\alpha-1}(1-x)^{\beta-1}\text{ if }x\in[0,1]\\0\text{ otherwise.}\end{cases}\quad\text{with shape parameters }\alpha,\beta>0
$$
where the Gamma function defined as
$$
\Gamma(a)=\int_0^\infty\xi^{a-1}e^{-\xi}d\xi
$$
as a generalisation of the factorial to non-integers.It has the property $\Gamma(a)=(a-1)!$

Expectation: $\mathbb E[X]=\frac{\alpha}{\alpha+\beta}$
Variance: $\text{Var}[X]=\frac{\alpha\beta}{(\alpha+\beta)^2(\alpha+\beta+1)}$
