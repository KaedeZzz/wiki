---
source: "KaedeSync/_Knowledge/Mathematics/Probability Theory/Basics/Distributions/Gaussian Distribution.md"
ingested: 2026-06-09
---

A random variable $X$ is said to have a Gaussian (or Normal) distribution with mean $\mu$ and variance $\sigma^2$ if:

$$ X\sim\mathcal N(\mu, \sigma^2)\Leftrightarrow f_X(x)=\frac1{\sqrt{2\pi\sigma^2}}\exp({-\frac{(x-\mu)^2}{2\sigma^2}}) $$

$\mathcal N(0,1)$ is called the standard Gaussian distribution.

$$ Y\sim \mathcal N(0,1)\Leftrightarrow X=\mu+\sigma Y\sim\mathcal N(\mu,\sigma^2) $$

The cumulative distribution function of $Y\sim\mathcal N(0, 1)$ is:

$$ F_Y(y)=\Phi(y)=\frac1{\sqrt{2\pi}}\int_{-\infty}^ye^{-\frac{\xi^2}2}d\xi $$

It is easy to verify that $\Phi(1/2)=0$ and $\Phi(-y)=1-\Phi(y)$

In the following, let $X=\mu+\sigma Y$ with $Y\sim\mathcal N(0,1)$:
Expectation: $\mathbb E[X]=\mu,\mathbb E[Y]=0,\mathbb E[X]=\sigma\mathbb E[Y]+\mu$
Variance: $\text{Var}[X]=\sigma^2,\text{Var} [Y]=1,\text{Var}[X]=\mathbb E[X^2]-\mathbb E[X]^2=(\sigma^2+\mu^2)-\mu^2=\sigma^2$
Mode: $x_{\max}=\mu$
Quartile: $Q_p=\mu+\sigma\Phi^{-1}(p)$
Skewness: $0$

Further links:
[[Multivariate Gaussian]]
