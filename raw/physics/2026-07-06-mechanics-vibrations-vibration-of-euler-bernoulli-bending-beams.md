---
source: KaedeSync/_Knowledge/Physics/Mechanics/Vibrations/Vibration of Euler-Bernoulli Bending Beams.md
ingested: 2026-07-06
---

[[1D Vibration Equations]]

![[Equation of Motion for Euler-Bernoulli Bending Beam]]

Note that, because this differential equation is 4-th order, we would expect 4 arbitrary constants, which results in the need of 4 boundary conditions.

Boundary conditions:
1. Clamped in
At $x=0$:
$$
\begin{align}
y & =0\text{ (no displacement)} \\
\frac{{\partial y}}{\partial x} & =0\text{ (no rotation)}
\end{align}
$$
2. Pinned (or hinged) boundary
At $x=0$:
$$
\begin{align}
y & =0 \text{ (no displacement)} \\
EI \frac{{\partial ^{2}y}}{\partial x^{2}} & =0\text{ (no bending moment)}
\end{align}
$$
3. Free boundary
At $x=0$:
$$
\begin{align}
EI \frac{{\partial ^{2}y}}{\partial x^{2}} & =0\text{ (no bending moment)} \\
EI \frac{{\partial ^{3}y}}{\partial x^{3}} & =0\text{ (no shear force)}
\end{align}
$$

###### Solution

Time-harmonic solution:
$$
y(x,t)=U(x)e^{i\omega t}
$$
substitute into the PDE without external force to get:
$$
EI \frac{{\partial^{4}U}}{\partial x^{4}}-\rho A\omega ^{2}U=0
$$
this is a fourth order PDE, so the general solution is:
$$
U(x)=C_{1}e^{ikx}+C_{2}e^{-ikx}+C_{3}e^{kx}+C_{4}e^{-kx}
$$
with
$$
k^{4}=\omega ^{2} \frac{\rho A}{EI}
$$
Note that, within the complete solution:
- $e^{i\omega t}e^{ikx}$ describes sinusoidally travelling wave.
- $e^{i\omega t}e^{kx}$ describes disturbances that do not travel but decay exponentially along the beam. These are known as **evanescent waves** or ‘near fields’ because their effect is spatially localised.

###### Modes and Natural Frequencies

Real form of modeshapes:
$$
U(x)=D_{1}\cos kx+D_{2}\sin kx+D_{3}\cosh kx+D_{4}\sinh kx
$$

![[Modes of a Pinned-pinned Beam]]

![[Modes of a Free-free Beam]]

![[Modes of a Clamped-free Beam]]