---
source: KaedeSync/_Knowledge/Communications/Basics/Sampling.md
ingested: 2026-07-08
---

For $n=-\infty, \dots,-1,0,1,2,\dots,\infty$, obtained values of $f(nT)$ are the sampled version of $f(t)$. The practical procedure is known as analogue to digital conversion.

Sampled signal:
$$
\begin{aligned}
f_{s}(t)&=\sum_{n=-\infty}^{\infty}f(nT)\delta(t-nT) \\
&=\sum_{n=-\infty}^{\infty}f(t)\delta(t-nT) \\
&=f(t)\sum_{n=-\infty}^{\infty}\delta(t-nT) \\
&= f(t)\delta_{p}(t)
\end{aligned}
$$
Fourier series of $\delta_{p}(t)$: 
$$
\delta_{p}(t)=\sum_{n=-\infty}^{\infty}c_{n}e^{jn\omega_{0}t}\text{ where }\omega_{n}=\frac{2\pi}{T}\text{ and }c_{n}=\frac{1}{T}
$$
therefore,
$$
\begin{aligned}
f_{s}(t)&=f(t) \frac{1}{T}\sum_{n=-\infty}^{\infty}e^{jn\omega_{0}t} \\
&= \frac{1}{T}\sum_{n=-\infty}^{\infty}f(t)e^{jn\omega_{0}t}
\end{aligned}
$$
Thus, the [[Fourier Transform]] of the samples signal:
$$
F_{s}(\omega)=\frac{1}{T}\sum_{n=-\infty}^{\infty}F(\omega-n\omega_{0})
$$

![[Discrete-time Fourier Transform (DTFT)]]