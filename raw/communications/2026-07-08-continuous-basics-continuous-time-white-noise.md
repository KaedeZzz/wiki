---
source: KaedeSync/_Knowledge/Communications/Continuous/Basics/Continuous-time White Noise.md
ingested: 2026-07-08
---

$$
X(t)=\sum_{k=-\infty}^{\infty}X_{k}p_{T}(t-kT)
$$
with $X_{k}\sim \mathcal N(0,\sigma ^{2})$ and a pulse shape $p_{T}(t)$ in the limit as $T\to 0$ and $\sigma ^{2}\to \infty$

- Typically we will use a rectangular pulse of height $1$ and width $b$.
- We construct a signal starting at $-\frac{T}{2}$ and ending $\frac{T}{2}$, consisting of pulses modulated with independent Gaussian random variables $X_{k}\sim\mathcal N\left( 0, \frac{1}{b} \right)$ of variance $\frac{1}{b}$.

$$
X(t)=\sum_{k=-\frac{T}{2b}}^{\frac{T}{2b}-1}X_{k}p(t-kb)
$$

![[Frequency Domain Analysis of Continuous-time White Noise with Finite Variance]]

[[White Noise]]