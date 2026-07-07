---
source: KaedeSync/_Knowledge/Physics/Mechanics/Vibrations/Forced Harmonic Response to Harmonic Excitation.md
ingested: 2026-07-06
---

Forced harmonic input:
$$
\begin{align}
F(x=a,t)&=Fe^{i\omega t} \\
F(x\neq a,t)&=0
\end{align}
$$
Since free solution is sinusoidal, and that $y(0,t)=0$ and $y(L,t)=0$. the easiest choice:
$$
\begin{align}
U=A\sin\left( \frac{\omega x}{c} \right)\quad &\text{ for }0<x<a \\
U=B\sin\left( \frac{\omega (L-x)}{c} \right)\quad &\text{ for }a<x<L
\end{align}
$$
at $x=a$:
- the string has no break, so
$$
A\sin\left( \frac{\omega a}{c} \right)=B\sin\left( \frac{\omega(L-a)}{c} \right)
$$
- and the forces must balance:
$$
\begin{align}
F&=P \frac{{\partial y}}{\partial x} \rvert _{a^{-}}-P \frac{{\partial y}}{\partial x} \rvert _{a^{+}} \\
&=P\left\{  \frac{A\omega}{c}\cos\left( \frac{\omega a}{c} \right)+\frac{B\omega}{c}\cos\left( \frac{\omega(L-a)}{c} \right)  \right\}
\end{align}
$$
Solution gives:
$$
\begin{align}
A&=\frac{Fc}{\omega P} \frac{\sin\left( {\omega[L-a] / c}\right)}{\sin(\omega L /c)} \\
B&=\frac{Fc}{\omega P} \frac{\sin\left( {\omega a / c}\right)}{\sin(\omega L /c)}
\end{align}
$$

- There exists natural frequencies where $\omega_{n}L / c=n\pi$, but there would not be resonance where $\sin(\omega_{n}a / c)=0$ (nodes).
- The system poles are given (by resonant frequencies) as $s=in\omega,\quad n=-2,1,1,2,\dots$. Therefore the system is **marginally stable**: if the structure is perturbed, then it will continue to vibrate infinitely (without damping). (See [[Open Loop Stability Criterion]])

[[Harmonic Solution of Wave Equation]]