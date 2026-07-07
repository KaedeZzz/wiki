---
source: KaedeSync/_Knowledge/Physics/Mechanics/Vibrations/Plucked String Problem.md
ingested: 2026-07-06
---

**Transient Free Response to Initial Conditions**

Initial conditions for idealised pluck:
$$
\begin{align}
y(x,0)&=
\begin{cases}
y_{0} \frac{x}{a}\quad &0\leq x\leq a \\
y_{0} \frac{{L-x}}{L-a}\quad &a\leq x\leq L
\end{cases} \\
y(0,t)&=0 \\
y(L,t)&=0 \\
F(a,t)&=
\begin{cases}
F_{0} \quad &\text{for }t<0 \\
0 \quad &\text{for }t>0
\end{cases}
\end{align}
$$

![[Equation of Free Vibration of String]]

Consider [[Harmonic Free Motion Theorem]], we know that the equation of free motion is then:
$$
y(x,t)=\sum_{n}b_{n}\sin\left(  \frac{n\pi x}{L} \right)\cos(\omega_{n}t+\phi)
$$
Differentiate with respect to time gives initial velocity: we know that initial velocity is $0$ everywhere, so $\phi=0$.

Consider a Fourier series for the triangle initial shape of string, we eventually have:
$$
b_{n}=\frac{{2y_{0}L^{2}}}{n^{2}\pi ^{2}a(L-a)}\sin \frac{n\pi a}{L}
$$
Putting all together, the motion of the string is given by:
$$
y(x,t)=DC(=0)+\sum_{n}\frac{{2y_{0}L^{2}}}{n^{2}\pi ^{2}a(L-a)}\sin \left( \frac{n\pi a}{L} \right)\sin\left(  \frac{n\pi x}{L} \right)\cos(\omega_{n}t+\phi)
$$

[[Vibration Modes]]