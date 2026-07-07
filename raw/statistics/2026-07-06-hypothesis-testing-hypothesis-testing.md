---
source: KaedeSync/_Knowledge/Statistics/Hypothesis Testing/Hypothesis Testing.md
ingested: 2026-07-06
---


A result has **statistical significance** when it is very unlikely to have occured given the *null hypothesis* is true.
A **null hypothesis** $\mathcal H_0$ is typically a statement of “no effect” or “no difference”.

We define the p-value of a result as the probability of obtaining a result at least as extreme, given $\mathcal H_0$ is true.

Choosing a significance level, denoted by $\alpha$ (typically 0.01 or 0.05). If $p<\alpha$, the result is unlikely to happen, so we reject $\mathcal H_0$.

In other sense, suppose we have a sequence of data $X_{1},\dots,X_{n}$ and knowledge that *one* of the following is true:
$$
\begin{align}
H_{0}:X_{1},\dots,X_{n}\sim i.i.d.\quad P \\
H_{1}:X_{1},\dots,X_{n}\sim i.i.d.\quad Q
\end{align}
$$
based on data we have to decide which one is true.