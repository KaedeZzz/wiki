---
source: KaedeSync/_Knowledge/Physics/Mechanics/Dynamical Systems/Koopman Operator Theory/Koopman Mode Decomposition.md
ingested: 2026-07-06
---

Individual measurements can be arranged in a vector:
$$
g(\mathbf{x})=
\begin{bmatrix}
g_{1}(\mathbf{x}) \\
g_{2}(\mathbf{x}) \\
\vdots \\
g_{p}(\mathbf{x})
\end{bmatrix}
$$
Each of the individual measurements may be expanded in terms of the [[Koopman Eigenfunction]] $\psi_{j}(x)$, which provides a basis for [[Hilbert Space]]:
$$
g_{i}(\mathbf{x})=\sum_{j=1}^{\infty}v_{ij}\psi_{j}(\mathbf{x})
$$
The vector of observables may be similarly expanded:
$$
\mathbf{g}(\mathbf{x})=\sum_{j=1}^{\infty}\psi_{j}(\mathbf{x})\mathbf{v}_{j}
$$
where $\mathbf{v}_{j}$ is the $j$-th *Koopman mode* associated with the eigenfunciton $\psi_{j}$.
*The Koopman eigenfunctions are orthonormal for conservative systems*, and it is possible to compute the Koopman modes directly by projection:
$$
\mathbf{v_{j}}=\begin{bmatrix}
\langle\psi_{j},g_{1}\rangle \\
\langle\psi_{j},g_{2}\rangle \\
\vdots \\
\langle\psi_{j},g_{p}\rangle
\end{bmatrix}
$$
where $\langle\cdot,\cdot\rangle$ is the standard inner product of functions in Hilbert space.

It is possible to represent the dynamics of the measurements $g$ as follows:
$$
\begin{align}
\mathbf{g}(\mathbf{x}_{k})=\mathcal K^{k}_{\Delta t}\mathbf{g}(\mathbf{x}_{0})&=\mathcal K^{k}_{\Delta t}\sum_{j=0}^{\infty}\psi_{j}(\mathbf{x}_{0})\mathbf{v}_{j} \\
&=\sum_{j=0}^{\infty}\mathcal K^{k}_{\Delta t}\psi_{j}(\mathbf{x}_{0})\mathbf{v}_{j} \\
&=\sum_{j=0}^{\infty}\lambda_{j}^{k}\psi_{j}(\mathbf{x}_{0})\mathbf{v}_{j}
\end{align}
$$
The sequence of triples, $\{ (\lambda_{j},\phi_{j},\mathbf{v}_{j}) \}_{j=0}^{\infty}$ is known as the *Koopman mode decomposition*.