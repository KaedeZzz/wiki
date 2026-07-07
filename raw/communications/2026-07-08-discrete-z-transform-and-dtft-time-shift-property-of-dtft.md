---
source: KaedeSync/_Knowledge/Communications/Discrete/z-Transform and DTFT/Time shift property of DTFT.md
ingested: 2026-07-08
---

[[Fourier Transform]]
$$
\begin{align}
\text{Let }u'&=\{ u_{k-a} \}: \\
U'(\theta)&= \sum_{k=-\infty}^{\infty}u_{k-a}e^{-jk\theta} \\
&= \sum_{k'=-\infty}^{\infty}u_{k'}e^{-j(k'+a)\theta} \\
&=e^{-ja\theta}U(\theta)
\end{align}
$$