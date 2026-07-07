---
source: KaedeSync/_Knowledge/Communications/Continuous/Fourier Transform/Discrete-time Fourier Transform (DTFT).md
ingested: 2026-07-08
---

[[Fourier Transform]]

Key idea: extract continuous frequency spectrum from discrete signals.

**Definition** from a discrete-time signal:
$$
U(\theta)=\sum_{k=-\infty}^{\infty}u_{k}e^{-jk\theta}
$$
which (might be?) equivalent to [[Two-sided z-Transform]] with $D=e^{-j\theta}$.

Definition from sampling of continuous signal:
$$
\begin{aligned}
F_{s}(\omega)&=\int_{-\infty}^{+\infty}f_{s}(t)e^{-j\omega t}dt \\
&= \int_{-\infty}^{+\infty}\left\{  \sum_{n=-\infty}^{\infty}f(t)\delta(t-nT)  \right\}e^{-j\omega t}dt \\
&= \sum_{n=-\infty}^{\infty}\left\{  \int_{-\infty}^{+\infty}f(t)e^{-j\omega t}\delta(t-nT)  \right\}dt \\
&= \sum_{n=-\infty}^{\infty}f(nT)e^{-jn\omega T}
\end{aligned}
$$
Definition from [[z-Transform]]: for [[Semi-Infinite Sequence]] signal,
$$
U(\theta)=U(z)\text{ for }z=e^{j\theta}
$$
equivalent to the z-transform on the unit circle.
