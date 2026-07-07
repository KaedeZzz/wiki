---
source: KaedeSync/_Knowledge/Physics/Mechanics/Langrangian/Lagrange for Small Motions.md
ingested: 2026-07-06
---

Consider small vibrations about a stable equilibrium position where $q_{1}=q_{2}=\dots=0$. Taylor expansion of $V(\mathbf{q})$ is:
$$
\begin{align}
V(q_{1},q_{2},\dots,q_{N})=V_{0}&+\frac{{\partial V}}{\partial q_{1}}q_{1}+\frac{{\partial V}}{\partial q_{2}}q_{2}+\dots+\frac{{\partial V}}{\partial q_{2}}q_{2} \\
&+\frac{1}{2}(\frac{{\partial ^{2} V}}{\partial q_{1}^{2}}q_{1}^{2}+\dots+\frac{{\partial ^{2} V}}{\partial q_{1}\partial q_{2}}q_{1}q_{2}+\dots) \\
&+\dots
\end{align}
$$

1. The constant term $V_{0}$ can be ignored
2. The equilibrium position is a stationary point, so
$$
\frac{{\partial V}}{\partial q_{j}}\rvert_{eqn}=0
$$
3. Ignore terms of order higher than $2$ because of small motions assumption.

Therefore, $V(\mathbf{q})$ can be expressed as:
$$
V=\frac{1}{2}\sum_{j=1}^{N}\sum_{k=1}^{N} \frac{{\partial ^{2}V}}{\partial q_{j}\partial q_{k}}q_{j}q_{k}
$$
This is so-called "*quadratic form*". It can be written in **matrix form**:
$$
V=\frac{1}{2} \mathbf{q}^{T}\mathbf{Kq}
$$
where $\mathbf{K}$ is symmetric.

In a similar way, kinetic energy can be written as
$$
T=\frac{1}{2} \mathbf{\dot{q}}^{T}\mathbf{M \dot{q}}
$$
*We have omitted dependence of $T$ on $q_{j}$ because for small vibrations this dependence can be approximated by evaluating $M_{jk}$ at the equilibrium position $\mathbf{q}=0$.*

[[Lagrange's Equation for Dynamical Systems]]