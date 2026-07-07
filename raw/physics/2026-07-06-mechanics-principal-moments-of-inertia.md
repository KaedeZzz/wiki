---
source: KaedeSync/_Knowledge/Physics/Mechanics/Principal Moments of Inertia.md
ingested: 2026-07-06
---

For the eigenvalue problem
$$
\mathbf{I}_{P}\mathbf{\omega}=\lambda \mathbf{\omega}
$$
the solution of eigenvalues, $\lambda$, are known as principal moments of inertia (of different [[Principal Axes of Inertia]]).

Rotation of the [[Inertia Matrix]] to principal axes of inertia is essentially a diagonalisation:
$$
\mathbf{I}_{P}=\begin{bmatrix}
A & 0 & 0 \\
0 & B & 0 \\
0 & 0 & C
\end{bmatrix}
$$
where $A,B,C$ are eigenvalues (principal moments).
Then, from $\mathbf{h}_{P}=\mathbf{I}_{P}\mathbf{\omega}$, we can obtain:
$$
\mathbf{\omega}=\begin{bmatrix}
\omega_{1} \\
\omega_{2} \\
\omega_{3}
\end{bmatrix}
\implies 
\mathbf{h}_{P}=
\begin{bmatrix}
A\omega_{1} \\
B\omega_{2} \\
C\omega_{3}
\end{bmatrix}
$$
which is much simpler to work with.