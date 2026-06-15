---
source: "KaedeSync/_Knowledge/Mathematics/Probability Theory/Random Processes/Power Spectral Density Function.md"
ingested: 2026-06-09
---

[[Fourier Transform]] of $C_{x x}(t)$:
$$
\hat{ x}(f)=\int_{\mathbb{R}}e^{-i 2\pi ft }x(t)dt\implies S_{x x}(f)=|\hat{x}(f)|^{2}=\int_{\mathbb{R}}e^{-i 2\pi ft }C_{x x}(t)dt
$$

Discrete-time case, for stochastic signal:
$$
\Phi_{XX}(\theta)=\lim_{ N \to \infty } \frac{1}{N}\mathbb{E}\{|X(\theta)|^{2}\}=\lim_{ N \to \infty } \frac{1}{N}\mathbb{E}\{X(\theta)X^{*}(\theta)\}
$$
where
$$
X(\theta)=\sum_{k=-\left\lfloor  \frac{N}{2}+1  \right\rfloor }^{\lfloor \frac N2 \rfloor }X_{k}e^{-jk\theta}
$$
is the DTFT of the signal.

The power spectral density for [[Discrete-time White Noise]] is $1$ for any $\theta$.