---
source: "KaedeSync/_Knowledge/Mathematics/Differential Equations/Wave Equation/Vibration Modes.md"
ingested: 2026-06-09
---

A vibration mode of a system is a free motion in which all points in the structure move sinusoidally at a particular frequency with a characteristic mode shape: all points moving **in equal or opposite phase** with each other. 

It is a particular case of separation of variables where:
$$
y=\mathrm{Re}\{ \mathbb{U}(x)e^{i\omega t} \}= U(x)\mathrm{Re}\{  e^{i(\omega t+\phi)}\}=U(x)\cos(\omega t+\phi)
$$
where $\mathbb{U}$ is complex and $U$ is real-valued.

Recall [[Harmonic Free Motion Theorem]]: for motion that is sinusoidal time, the solution for mode shape is the sum of two sinusoidal shapes that are opposite in shape. For standing wave, the two complex amplitudes are a conjugate pair; therefore, we can write the overall mode shape as:
$$
U(x)=A'\cos(kx)+B'\sin(kx)
$$
where $A'$ and $B'$ are real-valued.

boundary conditions for standing wave: $y=0\text{ at }x=0,L$
Therefore:
$$
\begin{aligned}
y(0,t)&=0,&\quad A'\cos k 0+B'\sin k 0 =0\implies A'=0 \\
y(L,t)&=0, &\quad B'\sin kL=0\implies k=\frac{n\pi}{L}
\end{aligned}
$$
The constant $B'$ is left undefined as it represents the **overall amplitude** of vibration and depends on the initial conditions.

Notice that there are infinite number of solutions, so there are an infinite number of modes in vibration for $n=0,1,2,\dots$, each associated with a mode shape $U_{n}(x)$ and natural frequency $\omega_{n}$

![[Pasted image 20250119204414.png]]

[[Wave Equation]]