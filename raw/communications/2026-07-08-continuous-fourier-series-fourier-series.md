---
source: KaedeSync/_Knowledge/Communications/Continuous/Fourier Series/Fourier Series.md
ingested: 2026-07-08
---

[[Fourier Analysis]]
Real Fourier Series:
Any function $g(t)$ which is **periodic** in the interval $[-\pi,\pi]$ has a real Fourier Series representation given by
$$
g(t)= \frac{a_{0}}{2}+\sum_{n=1}^\infty \{ a_{n}\cos(nt)+b_{n}\sin(nt) \}
$$
with the coefficients given by
$$
a_{n}=\frac{1}{\pi}\int_{-\pi}^\pi g(t)\cos(nt)dt
$$
$$
b_{n}=\frac{1}{\pi}\int_{-\pi}^\pi g(t)\sin(nt)dt
$$
Further links:
[[Complex Fourier Series]]
[[Fourier Series Transformations]]
[[Parseval's Theorem]]
