---
source: KaedeSync/_Knowledge/Physics/Mechanics/Dynamical Systems/Koopman Operator Theory/Koopman Eigenfunction.md
ingested: 2026-07-06
---

A discrete-time Koopman Eigenfunction $\psi(x)$ corresponding to eigenvalue satisfies:
$$
\psi(x_{k+1})=\mathcal K_{\Delta t}\psi(x_{k})=\lambda \psi(x_{k})
$$
in continuous time:
$$
\frac{d}{dt}\psi(x)=\mathcal K\psi(x)=\lambda \psi(x)
$$
applying chain rule:
$$
\frac{d}{dt}\psi(x)=\nabla \psi(x)\cdot \dot{x}=\nabla \psi(x)\cdot f(x)
$$
this results in a partial differential equation for the function $\psi(x)$:
$$
\nabla \psi(x)\cdot f(x)=\lambda \psi(x)
$$
which is a **non-linear** PDE.
With this PDE, it is possible to approximate the eigenfunctions either by solving for the [[Laurent Series]] or with data via regression; dynamics is assumed being both continuous and differrentiable.

Extension of [[Noether Theorem]] on Koopman eigenfunction: any symmetry in the governing equations gives rise to a new Koopman eigenfunction with $\lambda=0$.

Relationship between continuous and discrete-time eigenvalues:
if the continuous-time eigenvalues are given by $\lambda$, the discrete value is given by $e^{\lambda t}$.

$$
\lim_{ t \to 0 } \frac{\mathcal K_{t}\psi(x)-\psi(x)}{t}=\lim_{ t \to 0 } \frac{e^{\lambda t}\psi(x)-\psi(x)}{t}=\lambda \psi(x)
$$

![[Eigenvalue Lattice]]