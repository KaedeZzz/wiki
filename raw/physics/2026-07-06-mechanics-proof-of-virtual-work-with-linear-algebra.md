---
source: KaedeSync/_Knowledge/Physics/Mechanics/Proof of Virtual Work with Linear Algebra.md
ingested: 2026-07-06
---

Let $R$ be rigidity matrix.
Force equation:
$$
\begin{bmatrix}
H \\
V
\end{bmatrix}
=R\cdot \tau
$$
extension equation:
$$
e=R^{T}
\begin{bmatrix}
\delta_{H} \\
\delta_{V}
\end{bmatrix}
=R^{T}\delta
$$
Rearrange:
$$
\begin{bmatrix}
F \\
T
\end{bmatrix}
=
\begin{bmatrix}
R \\
I
\end{bmatrix}
\tau,\quad 
\begin{bmatrix}
R^{T} & I
\end{bmatrix}
\begin{bmatrix}
\delta \\
-e
\end{bmatrix}
=0
$$
call $A=\begin{bmatrix}R & I\end{bmatrix}^{T}$: $\begin{bmatrix}\delta & -e\end{bmatrix}^{T}$ is in the nullspace of $A$, therefore
$$
\begin{bmatrix}
F & T
\end{bmatrix}
\begin{bmatrix}
\delta \\
-e
\end{bmatrix}
=0
$$
That is, $F\cdot\delta-T\cdot e=0$. Proof.

[[Linear Algebra]], [[Mechanics and Dynamics]]