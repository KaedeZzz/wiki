---
source: KaedeSync/_Knowledge/Physics/Mechanics/Dynamical Systems/Dynamical System.md
ingested: 2026-07-06
---

A dynamical system is defined of its *memory* such that its output $y(t_{1})$ depends not just on current input $u(t_{1})$, but on past inputs $u(t)\text{ for }t<t_{1}$.

The **states** are a set of system variables to describe the memory, which must satisfy **two** properties:
- for any $t_{0}<t_{1}$, $x(t_{1})$ can be determined from $x(t_{0})$ and $\{ u(t)|t_{0}\leq t\leq t_{1} \}$
- $y(t_{1})$ is a *memoryless* function of $x(t_{1})$ and $u(t_{1})$.

That is, $x(t_{0})$ completely summarises the effect of inputs and states prior to $t_{0}$.

A dynamical system thus relates three variables:
$$
\begin{align}
\text{input } & \mathbf{u}(t)\in \mathbb{R}^{m} \\
\text{states } & \mathbf{x}(t)\in \mathbb{R}^{n} \\
\text{outputs }  & \mathbf{y}(t) \in \mathbb{R}^{t}
\end{align}
$$
