---
source: KaedeSync/_Knowledge/Communications/Continuous/Basics/Integral of Periodic Spectrum.md
ingested: 2026-07-08
---

[[Fourier Analysis]]
$$
\begin{aligned}
I&=\int_{-\infty}^{+\infty}\exp(j\omega t)d\omega\\
&=\lim_{ A \to \infty } \int_{-A}^{+A}\exp(j\omega t)d\omega\\
&=\lim_{ A \to \infty }\left[ \frac{e^{j\omega t}}{jt}\right]^A_{-A}\\
&=\lim_{ A \to \infty }\left(2 \frac{\sin(At)}{t}\right)\\
&=\lim_{ A \to \infty } 2\pi f_{3}(t;A)\\
&=2\pi\delta(t)
\end{aligned}
$$
Delta function: see [[Dirac Delta Function]]
