---
source: "KaedeSync/_Knowledge/Mathematics/Calculus/Vector Calculus/Jacobian Flip.md"
ingested: 2026-06-09
---

#ESSENTIAL 
Sometimes it is difficult to solve for determinant of [[Jacobian]] in one direction, but easy in the other direction. For example, for
$$
\begin{align}
r&=\sqrt{ x^{2}+y^{2} } \\
\theta &= \tan^{-1}(y /x)
\end{align}
$$
it is very hard to solve for $\partial \theta / \partial x$, etc. But in the other way round:
$$
\begin{align}
x&=r\cos \theta \\
y&=r\sin \theta
\end{align}
$$
It is feasible to obtain that
$$
\frac{{\partial (x,y)}}{\partial(r, \theta)}=\det \mathbf{J}=r
$$
