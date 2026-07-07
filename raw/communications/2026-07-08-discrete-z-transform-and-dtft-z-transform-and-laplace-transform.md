---
source: KaedeSync/_Knowledge/Communications/Discrete/z-Transform and DTFT/z-Transform and Laplace transform.md
ingested: 2026-07-08
---

Applying the [[Laplace Transform]] to a "train of impulses" sampled signal:
$$
\begin{align}
W_{s}(s)&=\int_{0}^{\infty}w_{s}(t)e^{-st}dt \\
&=\int_{0}^{\infty}\sum_{k=0}^{\infty}w(kT)\delta(t-kT)e^{-st}dt \\
&= \sum_{k=0}^{\infty}w(kT)e^{-skT} \\
&=\sum_{k=0}^{\infty}w_{k}z^{-k}
\end{align}
$$
The [[z-Transform]] is equivalent to the Laplace transform of the sampled 'impulse train' signal using a mapping from the Laplace to the $z$ domain:
$$s\to z=e^{sT}$$
