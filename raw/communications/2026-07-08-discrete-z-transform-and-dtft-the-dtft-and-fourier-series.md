---
source: KaedeSync/_Knowledge/Communications/Discrete/z-Transform and DTFT/The DTFT and Fourier Series.md
ingested: 2026-07-08
---

See: [[Fourier Series]] and [[Discrete-time Fourier Transform (DTFT)]]

DTFT:
$$
S(\theta)=\sum_{k=-\infty}^{\infty}s_{k}e^{-j\theta k}\quad s_{k}=\frac{1}{2\pi}\int_{-\pi}^{\pi}S(\theta)e^{jk\theta}d\theta
$$
Fourier series:
$$
f(t)=\sum_{k=-\infty}^{\infty}c_{k}e^{jkt}\quad c_{k}=\frac{1}{2\pi}\int_{-\pi}^{\pi}f(t)e^{-jkt}
$$
Fourier Series $\leftrightarrow$ DTFT on unit circle **with time and frequency domains swapped**