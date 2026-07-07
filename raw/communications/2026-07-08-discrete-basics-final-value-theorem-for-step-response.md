---
source: KaedeSync/_Knowledge/Communications/Discrete/Basics/Final Value Theorem for Step Response.md
ingested: 2026-07-08
---

[[z-Transform]] of step input:
$$
U(z) =\frac{z}{z-1}
$$

apply [[Final Value Theorem for z-Transform]]:
$$
\begin{align}
\lim_{ k \to \infty }y_{k} & =\lim_{ z \to 1 }(z-1)G(z)U(z) \\
 & =\lim_{ z \to 1 }(z-1)G(z)\left( \frac{z}{z-1} \right) =G(1)
\end{align}
$$