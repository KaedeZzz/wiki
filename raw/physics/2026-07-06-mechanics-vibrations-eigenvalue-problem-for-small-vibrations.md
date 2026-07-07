---
source: KaedeSync/_Knowledge/Physics/Mechanics/Vibrations/Eigenvalue Problem for Small Vibrations.md
ingested: 2026-07-06
---

From [[Lagrange's Equation for Dynamical Systems]] we get:
$$
\mathbf{M} \ddot{\mathbf{q}}+\mathbf{Kq}=\mathbf{Q}
$$
This is a set of $N$-*coupled* second order differential equations that can be *uncoupled* using the natural modes. 
The natural motions are found by putting $\mathbf{Q}=\mathbf{0}$ and assuming solutions of the form:
$$
\mathbf{q}=\mathbf{u}e^{i\omega t}
$$
Therefore, we get the equation of motion:
$$
-\omega ^{2}\mathbf{Mu}+\mathbf{Ku}=\mathbf{Q}
$$

![[Equation of Motion for Small Motion]]

This is a standard form of the eigenvalue problem, which can be solved for the natural frequencies $\omega=\omega_{n}$ and the natural mode shapes $\mathbf{u}^{(n)}$.

Procedure:
1. Solve $\det(\mathbf{K}-\omega ^{2}\mathbf{M})=0$
2. For each $\omega_{n}$, solve the simultaneous equations $\mathbf{Ku}=\omega_{n} ^{2}\mathbf{Mu}$ for the mode shape $\mathbf{u}^{(n)}$

Since both $\mathbf{K}$ and $\mathbf{M}$ are symmetric, it can be shown that all $\omega_{n}$ are real and all eigenvectors $\mathbf{u}^{(n)}$ are orthogonal.
