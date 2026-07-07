---
source: KaedeSync/_Knowledge/Physics/Mechanics/Dynamical Systems/Linearisation of State-space Dynamical System Model.md
ingested: 2026-07-06
---

Suppose we have a nonlinear *time-invariant* system in state-space form:
$$
\mathcal S
\begin{cases}
\dot{\mathbf{x}}(t)=\vec{f}(\mathbf{x}(t),\mathbf{u}(t)) \\
{\mathbf{y}}(t)=\vec{g}(\mathbf{x}(t),\mathbf{u}(t))
\end{cases}
$$
Let $\mathbf{x}_{e}$ be an equilibrium state for the system when $\mathbf{u}(t)=\mathbf{u}_{e}$, i.e. $\vec{f}(\mathbf{x}_{e},\mathbf{u}_{e})=0$. 
Let $\mathbf{y}_{e}=\vec{g}(\mathbf{x}_{e},\mathbf{u}_{e})$.
Consider small perturbation from the equilibrium, that is:
$$
\begin{align}
\mathbf{x}(t)=\mathbf{x}_{e}+\delta \mathbf{x} \\
\mathbf{u}(t)=\mathbf{u}_{e}+\delta \mathbf{u} \\
\mathbf{y}(t)=\mathbf{y}_{e}+\delta \mathbf{y}
\end{align}
$$
A Taylor series expansion of $\dot{\mathbf{x}}(t)$ gives:
$$
\begin{align}
\dot{\mathbf{x}}(t) & =\dot{\mathbf{x}}_{e}+\dot{\delta \mathbf{x}} \\
 & =\vec{f}(\mathbf{x}_{e},\mathbf{u}_{e})+\frac{{\partial \vec{f}}}{\partial \mathbf{x}}\rvert_{\mathbf{x}_{e},\mathbf{u}_{e}}\delta \mathbf{x}+\frac{{\partial \vec{f}}}{\partial \mathbf{u}}\rvert_{\mathbf{x}_{e},\mathbf{u}_{e}}\delta \mathbf{u}+\text{Remainder}
\end{align}
$$
thus for small $\delta \mathbf{x},\delta \mathbf{u}$,
$$
\begin{align}
\dot{\delta\mathbf{x}}(t) & \approx \mathbf{A}\delta \mathbf{x}+\mathbf{B}\delta\mathbf{u} \\
\text{where }\mathbf{A} & =\frac{{\partial \vec{f}}}{\partial \mathbf{x}}\rvert_{\mathbf{x}_{e},\mathbf{u}_{e}}, \mathbf{B}=\frac{{\partial \vec{f}}}{\partial \mathbf{u}}\rvert_{\mathbf{x}_{e},\mathbf{u}_{e}}
\end{align}
$$
and note that the Jacobian expands as
$$
\frac{{\partial \vec{f}}}{\partial \mathbf{x}}\rvert_{\mathbf{x}_{e},\mathbf{u}_{e}}=
\begin{bmatrix}
\frac{{\partial f_{1}}}{\partial x_{1}}  & \frac{{\partial f_{1}}}{\partial x_{2}} & \dots & \frac{{\partial f_{1}}}{\partial x_{n}} \\
\frac{{\partial f_{2}}}{\partial x_{1}} & \frac{{\partial f_{2}}}{\partial x_{2}} & \dots & \frac{{\partial f_{2}}}{\partial x_{n}} \\
\vdots & \vdots &  & \vdots \\
\frac{{\partial f_{n}}}{\partial x_{1}} & \frac{{\partial f_{n}}}{\partial x_{2}} & \dots & \frac{{\partial f_{n}}}{\partial x_{n}}
\end{bmatrix}_{\mathbf{x}=\mathbf{x}_{e},\mathbf{u}=\mathbf{u}_{e}}
$$
Similarly, 
$$
\delta\mathbf{y}(t) \approx \mathbf{C}\delta \mathbf{x}+\mathbf{D}\delta\mathbf{u}
$$
The linearised system equations are thus
$$
\begin{cases}
\dot{\delta\mathbf{x}}(t)  = \mathbf{A}\delta \mathbf{x}+\mathbf{B}\delta\mathbf{u} \\
\delta\mathbf{y}(t) =  \mathbf{C}\delta \mathbf{x}+\mathbf{D}\delta\mathbf{u}
\end{cases}
$$
For systems that are both linear and time-invariant, we simply use the standard form:
$$
\mathcal S
\begin{cases}
\dot{\mathbf{x}}(t)  = \mathbf{A} \mathbf{x}(t)+\mathbf{B}\mathbf{u}(t) \\
\mathbf{y}(t) =  \mathbf{C} \mathbf{x}(t)+\mathbf{D}\mathbf{u}(t)
\end{cases}
$$
