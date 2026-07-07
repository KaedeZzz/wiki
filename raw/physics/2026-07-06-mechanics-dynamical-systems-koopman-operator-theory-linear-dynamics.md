---
source: KaedeSync/_Knowledge/Physics/Mechanics/Dynamical Systems/Koopman Operator Theory/Linear Dynamics.md
ingested: 2026-07-06
---

[[Linear Algebra]] and [[Differential Equations]]
Whenever possible, it is desirable to work with linear dynamics of the form
$$
\frac{d}{dt}x=Ax
$$
solution is given by:
$$
x(t_{0}+t)=e^{At}x(t_{0})
$$
The dynamics are entirely characterised by the eigenvalues and eigenvectors of the matrix $A$, given by the spectral decomposition of $A$:

![[Eigen-decomposition]]

In this case it is possible to write $A=T\Lambda T^{-1}$ and the solution becomes
$$
x(t_{0}+t)=Te^{\Lambda t}T^{-1}x(t_{0})
$$
(eigenvalues of $e^{At}$ is $e^{\Lambda t}$)

The matrix $T^{-1}$ defines a transformation $z=T^{-1}x$ into intrinsic eigenvector coordinates $z$ where the dynamics become decoupled:
$$
\frac{d}{dt}z=\Lambda z
$$
