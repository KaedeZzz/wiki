---
source: KaedeSync/_Knowledge/Information Theory/Basics/Mutual Information.md
ingested: 2026-07-06
---

Measure of mutual dependence between the two variables.
$$
\begin{aligned}
I(X;Y)&\equiv H(X)-H(X|Y) \\
&= \sum_{y \in Y}\sum_{x \in X}P_{(X,Y)}(x,y)\log\left( \frac{P_{(X,Y)}(x,y)}{P_{X}(x)P_{Y}(y)}\right)\\
&=I(Y;X)
\end{aligned}
$$
*"Reduction in the uncertainty of $X$ when observing Y"*

[[Information Theory]], [[Joint and Conditional Entropy]]