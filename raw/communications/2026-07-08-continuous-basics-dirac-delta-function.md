---
source: KaedeSync/_Knowledge/Communications/Continuous/Basics/Dirac Delta Function.md
ingested: 2026-07-08
---

[[Fourier Analysis]]
Consider a rectangular pulse $f_{1}(t;\epsilon)$:
![[Pasted image 20240924170011.png]]
The pulse is designed such that it has unit area:
$$
\int^{+\infty}_{-\infty}f_{1}(t;\epsilon)dt=1\text{ for all }\epsilon>0
$$
The $\delta$-function can be defined as a limiting case:
$$
\delta(t)=\lim_{ \epsilon \to 0 }f_{1}(t;\epsilon)
$$
Two familiar properties are
$$
\delta(t)=0\text{ for }t\neq 0
$$
and
$$
\int^{+\infty}_{-\infty}\delta(t)dt=1
$$
Other definitions can also be used, including
$$
\begin{aligned}
f_{2}(t;\epsilon)&= \frac{\epsilon}{\epsilon ^{2}\pi^{2}+t^{2}} \\
f_{3}(t;\epsilon)&= \frac{\sin(at)}{\pi t}
\end{aligned}
$$
Sifting: see [[Sifting Property]]

