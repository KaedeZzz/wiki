---
source: KaedeSync/_Knowledge/Physics/Mechanics/Vibrations/Modes of a Free-free Beam.md
ingested: 2026-07-06
---

$$
\begin{align}
U''(0) & =0 \implies -D_{1}+D_{3}=0\\
U'''(0) & =0 \implies -D_{2}+D_{4}=0\\
U''(L) & =0 \implies -D_{1}\cos(kL)-D_{2}\sin (kL)+D_{1}\cosh(kL)+D_{2}\sinh(kL)=0\\
U'''(L) & =0\implies D_{1}\cos(kL)-D_{2}\sin (kL)+D_{1}\cosh(kL)+D_{2}\sinh(kL)=0
\end{align}
$$

which can be written as a matrix:
$$
\begin{bmatrix}
-\cos(kL)+\cosh(kL) & -\sin(kL)+\sinh(kL) \\
\sin(kL)+\sinh(kL) & -\cos(kL)+\cosh(kL)
\end{bmatrix}
\begin{bmatrix}
D_{1} \\
D_{2}
\end{bmatrix}
=0
$$

The non-trivial solution occurs when the determinant is zero:
$$
\begin{align}
\det=0 & \implies \cos ^{2}(kL)-2\cos(kL)\cosh(kL)+\cosh ^{2}(kL)-\sinh ^{2}(kL)+\sin ^{2}(kL)=0 \\
 & \implies \cos(kL)\cosh(kL)=1
\end{align}
$$
Approximate non-zero solutions are
$$
k_{n}\approx\left( n+\frac{1}{2} \right) \frac{\pi}{L}
$$
Giving non-zero natural frequencies
$$
\omega_{n}\approx\left(  \frac{\left( n+\frac{1}{2} \right)\pi}{L} \right)^{2}\sqrt{ \frac{EI}{\rho A} }
$$

To obtain a given mode shape, use $D_{1}=D_{3}, D_{2}=D_{4}$, and
$$
D_{2}=D_{1}\frac{\cosh kL-\cos kL}{\sin kL-\sinh kL}
$$
