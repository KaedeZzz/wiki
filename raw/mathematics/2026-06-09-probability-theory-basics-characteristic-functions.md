---
source: "KaedeSync/_Knowledge/Mathematics/Probability Theory/Basics/Characteristic Functions.md"
ingested: 2026-06-09
---

$$
\begin{aligned}
\phi_{X}(t)&=\mathbb{E}[\exp(itX)]\text{ for a random variable}\\
&=\mathbb{E}[\exp(i(\mathbf{t}^{T}\mathbf{X})]\text{ for a random vector} \\
&= \int_{-\infty}^{\infty}e^{itx}f(x)dx
\end{aligned}
$$
which is essentially [[Fourier Transform]] of the density.
Therefore, inverse density from C.F.:
$$
f(x)=\frac{1}{2\pi}\int_{-\infty}^{\infty}e^{-itx}\phi_{X}(t)dt
$$
Properties: 
$$
\begin{align}
\phi_{X}^{(k)}(0)&=i^{k}\mathbb{E}\{X^{k}\} \\
\phi_{X+a(t)}&=\phi_{X}(t)e^{iat} \\
\phi_{A\mathbf{X}+\mathbf{b}}(\mathbf{t})&=e^{i\mathbf{t}^{T}\mathbf{b}}\phi_{\mathbf{X}}(A^{T}\mathbf{t})
\end{align}
$$
for $X,Y$ independent,
$$
\begin{align}
\phi_{aX+bY}(t)&=\phi_{X}(at)\phi_{Y}(bt) \\
\end{align}
$$
if $\phi_{X}(t)=\phi_{Y}(t)$, $X$ and $Y$ has the same distribution.

C.F. of [[Gaussian Distribution]] $\mathcal N(0,1)$: $e^{- t^{2}/2}$

Derivation [[Weak Law of Large Numbers]] from Characteristic functions:
$$
\begin{align}
\phi_{n}(t)&=e^{it\mu} \\
\phi_{\frac{X}{n}}(t)&=\mathbb{E}\{e^{itX/n}\}=1+\frac{it\mu}{n}+O\left( \frac{1}{n^{2}} \right) \\
\lim_{ t \to \infty }\phi_{\frac{X}{n}}(t)&=1 
\end{align}
$$