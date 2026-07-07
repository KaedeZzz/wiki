---
source: KaedeSync/_Knowledge/Communications/Discrete/Basics/Power Series and Convolution.md
ingested: 2026-07-08
---

[[Formal Power Series]]

![[Dummy Polynomial]]

Consider the following polynomials:

$$
\begin{align}
c(D)&=c_{0}+c_{1}D \\
u(D)&=u_{0}+u_{1}D+u_{2}D^{2} \\
y(D)&=c(D)u(D)\\
&=c_{0}u_{0}+(c_{1}u_{0}+c_{0}u_{1})D+(c_{1}u_{1}+c_{0}u_{2})D^{2}+(c_{1}u_{2})D^{3}
\end{align}
$$
it is great to find that the coefficients of the product polynomial corresponds to the *convolution* of coefficients from the two polynomials!

Therefore polynomial multiplication is a resemblance with discrete convolution of $c=(c_{0},c_{1})$ and $u=(u_{0},u_{1},u_{2})$. Specifically, **[[Discrete Convolution]] of semi-infinite sequences is equivalent to multiplication of polynomials.**

Formal proof:
$$
u(D)=u_{0}+u_{1}D+u_{2}D^{2}+u_{3}D^{3}+\dots
$$
$$
\begin{align}
c(D)u(D)&=\left( \sum_{k=0}^{\infty} c_{k}D^{k}\right)\left(\sum_{m=0}^{\infty} u_{m}D^{m}\right) \\
&=\sum_{k=0}^{\infty}\sum_{m=0}^{\infty} c_{k}u_{m}D^{k+m} \\
&=\sum_{k=0}^{\infty}\sum_{n=k}^{\infty}c_{k}u_{n-k}D^{n} \\
\text{Note index boundary change!}&=\sum_{n=0}^{\infty}\left(\sum_{k=0}^{n}c_{k}u_{n-k}\right)D^{n} \\
&= \sum_{n=0}^{\infty}y_{n}D^{n} \text{ ,where }y=c*u
\end{align}
$$
*Explanation of Index change:* 
- *think about all possible pairs of $n$ and $k$ where $k$ goes to infinity and $n$ is always larger than or equal to $k$. The alignment of the pair is "triangular".* 
- *If we forget about $k$ and just look at what value $n$ can take, we find that it can also take values from $0$ to $\infty$.*
- *Then, given a $n$, what are the possible values of $k$? It is from $0$ to $n$.*
- *Therefore,*
$$
\sum_{k=0}^{\infty}\sum_{n=k}^{\infty}=\sum_{n=0}^{\infty}\sum_{k=0}^{n}
$$

