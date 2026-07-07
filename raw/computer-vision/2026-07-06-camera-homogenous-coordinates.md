---
source: KaedeSync/_Knowledge/Computer Vision/Camera/Homogenous Coordinates.md
ingested: 2026-07-06
---

Represent each point on a plane not by two numbers $\mathbf{x}=(x,y)$ but by three numbers $\tilde{\mathbf{x}}=(x_{1},x_{2},x_{3})$ such that
$$
\begin{bmatrix}
x \\
y
\end{bmatrix}
=
\begin{bmatrix}
x_{1} / x_{3} \\
x_{2} / x_{3}
\end{bmatrix}
$$
Therefore:
- For any non-zero number $\lambda$, $(\lambda x_{1},\lambda x_{2}, \lambda x_{3})$ denotes the same point as $(x_{1},x_{2},x_{3})$: it is only the ratios that matter.
- If $x_{3}=0$, then $x$ and $y$ are infinite but have definite ratio. The number $(x_{1},x_{2},0)$ denotes points at infinity.

[[Projection]]