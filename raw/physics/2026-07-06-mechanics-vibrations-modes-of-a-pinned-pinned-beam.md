---
source: KaedeSync/_Knowledge/Physics/Mechanics/Vibrations/Modes of a Pinned-pinned Beam.md
ingested: 2026-07-06
---

Boundary conditions:
$$
\begin{align}
U(0) & =0 \implies D_{1}+D_{3}=0\\
U''(0) & =0 \implies -D_{1}+D_{3}=0\\
U(L) & =0 \implies -D_{2}\sin(kL)+D_{4}\sinh(kL)=0\\
U''(L) & =0\implies D_{2}\sin(kL)+D_{4}\sinh(kL)=0
\end{align}
$$
which indicates:
$$
D_{1}=D_{3}=0,\quad  D_{2}\sin kL=D_{4}\sinh kL=0
$$
therefore:
$$
\begin{align}
D_{2}\sin(kL) & =0 
\implies D_{2}=0 \text{ OR } \sin(kL)=0 \\
kL & =n\pi \text{ for }n=1,2,\dots \\
D_{2}\sin(kL) & =0 
\implies D_{4}=0 \text{ OR } k=0 
\end{align}
$$
So that natural frequencies
$$
\omega_{n}=k_{n}^{2}\sqrt{ \frac{EI}{\rho A} }=\left( \frac{n\pi}{L} \right)^{2}\sqrt{ \frac{EI}{\rho A} }
$$
and the mode shapes are
$$
U_{n}(x)=\sin(k_{n}x)=\sin \frac{n\pi x}{L}
$$
the mode shapes are identical to a stretched string, but natural frequencies are not equally spaced, as $\omega_{n}\propto n^{2}$.

