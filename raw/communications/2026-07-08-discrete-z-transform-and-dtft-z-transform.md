---
source: KaedeSync/_Knowledge/Communications/Discrete/z-Transform and DTFT/z-Transform.md
ingested: 2026-07-08
---

[[Signal Processing]]

Discrete-time equivalent of [[Laplace Transform]]. (Is it really?)

For a signal $\{ u_{k} \}$, the z-transform is defined as
$$
U(z)=\sum_{k=0}^{\infty}u_{k}z^{-k}
$$
which is equivalent to a [[Formal Power Series]] with variable $D=z^{-1}$.

**Right-sided**
Note that z-transform ignores all signal values at negative times.

**Linearity**
z-transform is linear. An important implication is that
$$
\frac{d}{da}U(z)=\mathcal Z\left\{  \frac{du_{k}}{da}  \right\}_{k\geq 0}
$$

![[Two-sided z-Transform]]

![[Region of Convergence of z-Transform]]




