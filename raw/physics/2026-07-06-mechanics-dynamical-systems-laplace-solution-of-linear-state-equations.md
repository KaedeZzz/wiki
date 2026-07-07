---
source: KaedeSync/_Knowledge/Physics/Mechanics/Dynamical Systems/Laplace Solution of Linear State Equations.md
ingested: 2026-07-06
---

Solving the equation system
$$
\mathcal S
\begin{cases}
\dot{\mathbf{x}}(t)  = \mathbf{A} \mathbf{x}(t)+\mathbf{B}\mathbf{u}(t) \\
\mathbf{y}(t) =  \mathbf{C} \mathbf{x}(t)+\mathbf{D}\mathbf{u}(t)
\end{cases}
$$
with $\mathbf{x}(0)=\mathbf{x}_{0}$ gives:
$$
\begin{align}
s\mathbf{X}(s)-\mathbf{x}_{0} & =\mathbf{AX}(s)+\mathbf{BU}(s) \\
\mathbf{X}(s) & =(s\mathbf{I}-\mathbf{A})^{-1}\mathbf{x}_{0}+(s\mathbf{I}-\mathbf{A})^{-1}\mathbf{BU}(s) \\
\mathbf{Y}(s) & =\mathbf{C}(s\mathbf{I}-\mathbf{A})^{-1}\mathbf{x}_{0}+(\mathbf{D}+\mathbf{C}(s\mathbf{I}-\mathbf{A})^{-1}\mathbf{B})\mathbf{U}(s)
\end{align}
$$
which is a sum of initial condition response and input response.

#SUPO What happens if $s\mathbf{I}-\mathbf{A}$ is singular?

For $\mathbf{x}_{0}=\mathbf{0}$, 
$$
\mathbf{G}(s)=\mathbf{D}+\mathbf{C}(s\mathbf{I}-\mathbf{A})^{-1}\mathbf{B}
$$
is called the **transfer function matrix** where the entry $(i,j)$ gives the transfer function from $u_{j}$ to $y_{i}$.

[[Laplace Transform]], [[Linearisation of State-space Dynamical System Model]]