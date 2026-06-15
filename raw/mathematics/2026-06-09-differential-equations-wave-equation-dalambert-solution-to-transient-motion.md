---
source: "KaedeSync/_Knowledge/Mathematics/Differential Equations/Wave Equation/d'Alambert Solution to Transient Motion.md"
ingested: 2026-06-09
---

![[Wave Equation]]

Consider that $y(x,t=0)=y_{0}(x)$ and $\dot{y} (x,t=0)=0$:
$$
\begin{align}
f(x)+g(x)&=y_{0}(x) \\
-cf'(x)+cg'(x)&=0
\end{align}
$$
solution is simply:
$$
f(x)=g(x)=\frac{y_{0}(x)}{2}
$$
therefore, transient response:
$$
y(x,t)=\frac{1}{2}[y_{0}(x-ct)+y_{0}(x+ct)]
$$
Properties of $f$ and $g$: consider
- at $x=0$, $f(-ct)+g(ct)=0$
- at $x=L$, $f(L-ct)+g(L+ct)=0$

this gives $f(ct+L)=f(ct-L)$ which indicates $f$ (and $g$) are periodic over distance $2L$.