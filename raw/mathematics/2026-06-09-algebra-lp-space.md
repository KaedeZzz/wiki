---
source: "KaedeSync/_Knowledge/Mathematics/Algebra/lp Space.md"
ingested: 2026-06-09
---

For a real or complex number $p\geq 1$, the $l^{p}$ space is defined as:
$$
l^{p}=\left\{  x=(x_{1},x_{2},x_{3},\dots):\sum_{n=1}^{\infty}\lvert x_{n} \rvert ^{p}<\infty  \right\}
$$
That is, the set of all infinite sequences of numbers whose $p$-th powers are absolutely summable. In this case, each element has a [[Ip-Norm]] defined by
$$
\lVert x \rVert _{p}=\begin{cases}
\left( \sum_{n=1}^{\infty}\lvert x_{n} \rvert^{p}  \right)^{1/p} & \text{if }1\leq p \leq \infty \\
\sup_{n \in \mathbb{N}}\lvert x_{n} \rvert  & \text{if }p=\infty
\end{cases}
$$