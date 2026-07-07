---
source: KaedeSync/_Knowledge/Communications/Continuous/Fourier Series/Fourier Series Transformations.md
ingested: 2026-07-08
---

Linear scaling:
$$
g'(t)=ag\left( \frac{{t-b}}{\beta} \right) = \sum_{n=-\infty}^{+\infty}c'_{n}e^{j\omega'_{0}nt}\text{ where }c'_{n}=ac_{n}e^{-j\omega'_{0}nt}\text{ and }\omega'_{0}=\omega_{0 / \beta}
$$
Differentiation and Integration:
$$
\frac{dg(t)}{dt} \implies c'_{n}=jn\omega_{0}c_{n}
$$
$$
h(t)=\int g(t)dt\implies c'_{n}=
\begin{cases}
\frac{c_{n}}{jn\omega_{0}}&\text{ if }n\neq 0 \\
\frac{1}{T} \int_{0}^{T}h(t)dt&\text{ if }n=0
\end{cases}
$$
