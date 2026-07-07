---
source: KaedeSync/_Knowledge/Communications/Continuous/Fourier Transform/Fourier Transform.md
ingested: 2026-07-08
---

Defined for functions with *finite signal energy*.

$$
\begin{aligned}
F(\omega)&=\lim_{ T \to \infty } \int_{-\frac{T}{2}}^{\frac T 2}f(t)e^{-j\omega t}dt \\
&=\int_{-\infty}^{+\infty}f(t)e^{-j\omega t}dt
\end{aligned}

$$
Often referred to as the spectrum of Fourier integral.

Inverse Fourier Transform:
$$
f(t)=\frac{1}{2\pi}\int_{-\infty}^{+\infty}F(\omega)e^{j\omega t}d\omega
$$

Properties of Fourier Transform:
1. Linearity
2. Time scaling: $f(\alpha t)\leftrightarrow \frac{1}{\alpha}F\left( \frac{\omega}{\alpha} \right) \implies$ [[Heisenberg-Gabor Principle]]
3. Time shift: $f(t-t_{0})\leftrightarrow F(\omega)e^{-j\omega t_{0}}$
4. Frequency shift/Modulation: $e^{j\omega_{0} t}f(t)\leftrightarrow F(\omega-\omega_{0})$
5. Differentiation wrt t: $f^{(n)}(t)\leftrightarrow(j\omega)^{n}F(\omega)$
6. Duality: $f(t)\leftrightarrow F(\omega)\implies F(t)\leftrightarrow 2\pi f(-\omega)$
7. Convolution: $h(t)=f*g\implies H(\omega)=F(\omega)G(\omega)$
