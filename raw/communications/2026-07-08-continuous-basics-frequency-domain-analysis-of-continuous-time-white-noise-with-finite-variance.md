---
source: KaedeSync/_Knowledge/Communications/Continuous/Basics/Frequency Domain Analysis of Continuous-time White Noise with Finite Variance.md
ingested: 2026-07-08
---


- The [[Fourier Transform]] of a unit step $u(t)$ is $\pi\delta(\omega)+ \frac{1}{j\omega}$.
- Since $p(t)=u(t)-u(t-b)$, the Fourier transform of the rectangular pulse (using [[Time Shift Property of Discrete Transforms]]) is
$$
P(\omega)=\left( \pi\delta(\omega)+ \frac{1}{j\omega} \right)(1-e^{-jb\omega})
$$
- Hence the Fourier transform of the input signal *is the summation of rectangular pulses*:
$$
X(\omega)=\sum_{k=-\frac{T}{2b}}^{\frac{T}{2b}-1}X_{k}\left( \pi \delta(\omega)+ \frac{1}{j\omega} \right)(1-e^{-jb\omega})e^{-jkb\omega}
$$
where $e^{-jkb\omega}$ is again using time shift to obtain Fourier transform of $p(t-kb)$
- For $\omega\neq 0$, we can ignore the pulse function (it evaluates to $0$) in the expression to obtain
$$
X(\omega)=\sum_{k=-\frac{T}{2b}}^{\frac{T}{2b}-1}X_{k}\frac{1-e^{-jb\omega}}{j\omega} e^{-jkb\omega}
$$
- Now, in $S_{XX}(\theta)=\lim_{ N \to \infty } \frac{1}{N}\mathbb{E}[|X(\theta)|^{2}]$, so we compute
$$
\begin{align}
\frac{1}{T}\mathbb{E}[|X(\omega)|^{2}] & =\frac{1}{T}\mathbb{E}[X(\omega)X^{*}(\omega)] \\
 & =\frac{1}{T}\sum_{k=-\frac{T}{2b}}^{\frac T{2b}-1}\mathbb{E}[X_{k}^{2}]  \frac{{2-2\cos(b\omega)}}{\omega ^{2}}
\end{align}
$$
The expression does not depend on $k$ and recall that $\mathbb{E}[X_{k}^{2}]=\frac{1}{b}$

#TBD