---
source: KaedeSync/_Knowledge/Communications/Continuous/Fourier Series/Complex Fourier Series.md
ingested: 2026-07-08
---

Any function $g(t)$ which is **periodic** in the interval $[-\pi,\pi]$  has a [[Fourier Series]] representation given by
$$
g(t)=\sum_{n=-\infty}^\infty c_{n}e^{jnt}
$$
with coefficients:
$$
c_{n}=\frac{1}{2\pi}\int_{-\pi}^\pi g(t)e^{-jnt} dt
$$
- *(applies to any periodic interval of length $2\pi$, just difference in integration bounds)*

**For period $\neq 2\pi$:**
When a [[Periodic]] signal has period $T$ rather than $2\pi$, simply think of "stretching" the time axis by a factor of $T / 2\pi$. The complex Fourier Series then becomes:
$$
g(t)=\sum_{n=-\infty}^{+\infty}c_{n}e^{jn\omega_{0}t}
$$
where $\omega_{0}=2\pi / T$ is known as the "fundamental frequency". Here,
$$
c_{n}=\frac{1}{T}\int_{\alpha}^{\alpha+T}g(t)e^{-j\omega_{0}nt}dt
$$
