---
source: KaedeSync/_Knowledge/Physics/Mechanics/Dynamical Systems/Linearisation of Implicit State Equations.md
ingested: 2026-07-06
---

![[Implicit State Equation]]

At equilibrium:
$$
\vec{F}(\mathbf{0},\dot{\mathbf{x}}_{e},\mathbf{u}_{e})=\mathbf{0}
$$

Differentiation:
$$
\frac{{\partial \vec{F}}}{\dot{\partial \mathbf{x}}}|_{(\mathbf{0},\dot{\mathbf{x}}_{e},\mathbf{u}_{e})}\dot{\delta \mathbf{x}}+\frac{{\partial \vec{F}}}{\partial \mathbf{x}}|_{(\mathbf{0},\dot{\mathbf{x}}_{e},\mathbf{u}_{e})}\delta \mathbf{x}+\frac{{\partial \vec{F}}}{\partial \mathbf{u}}|_{(\mathbf{0},\dot{\mathbf{x}}_{e},\mathbf{u}_{e})}\delta \mathbf{u}=\mathbf{0}
$$
let it be
$$
\mathbf{L}\dot{\delta \mathbf{x}}+\mathbf{M}\delta \mathbf{x}+\mathbf{N}\delta \mathbf{u}=\mathbf{0}
$$
so
$$
\dot{\delta \mathbf{x}}=-\mathbf{L}^{-1}\mathbf{M}\delta \mathbf{x}-\mathbf{L}^{-1}\mathbf{N}\delta \mathbf{u}
$$
[[Linearisation of State-space Dynamical System Model]]