---
source: "KaedeSync/_Knowledge/Mathematics/Probability Theory/Basics/Probability Density Function.md"
ingested: 2026-06-09
---

A Probability density function (PDF) is a non-negative function,
$$
f(t)\geq 0 \text{ subject to } \int_{-\infty}^\infty f(t)dt=1
$$

For any event $E=[a, b]$, define $P(E)=\int_{a}^b f(t)dt$, that is, "what is the probability that $X$ lies in subset $E=[a, b]$ of the real line?" 

Note: definition implies $P(\{c\})=0 \implies P((a, b))=P([a, b])$

*How to define a probability space from a density?*

Define indicator function:

![[Indicator Function]]

Then define density function to have property $f(x)>0$ and $\int_{-\infty}^{\infty}f(X)=1$

Then, a probability space $(\mathbb{R},P)$ is defined where:
$$
P(A)=\int_{a}^b \mathbb{I}_{A}(t)f(t)dt
$$

PDF of discrete variable: i.e. transformation from [[Probability Mass Function]]
$$
f_X(x)=\sum_{k\in\mathbb X}P_X(k)\delta(x-k)
$$
Two random variables are independent if:
$$
f_{XY}(x,y)=f_{X}(x)f_{Y}(y)
$$
