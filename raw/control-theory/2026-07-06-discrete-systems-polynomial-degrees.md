---
source: KaedeSync/_Knowledge/Control Theory/Discrete Systems/Polynomial Degrees.md
ingested: 2026-07-06
---

For a linear system in canonical form,
$$
\begin{align}
G(z)= \frac{b(z)}{a(z)}&=\frac{{b_{0}+b_{1}z^{-1}+\dots+b_{m}z^{-m}}}{1+a_{1}z^{-1}+\dots+a_{n}z^{-n}} \\
&=\frac{{b_{0}z^{\max(m,n)}+\dots+b_{m}z^{\min(n-m,0)}}}{z^{\max(m,n)}+\dots+a_{n}z^{\min(m-n,0)}}
\end{align}
$$
therefore both polynomials have degree $\max(m,n)$.
