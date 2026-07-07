---
source: KaedeSync/_Knowledge/Information Theory/Basics/Properties of Mutual Information.md
ingested: 2026-07-06
---



1. $I(X;Y)=I(Y;X)$
2. $I(X;Y)=D(P_{XY}||P_{X}P_{Y})$
Proof:
$$
\begin{align}
I(X;Y) & =H(X)-H(X|Y) \\
 & =-\sum _{x}P_{X}(x)\log P_{X}(x)+\sum_{x,y}P_{XY}(x,y)\log P_{X|Y}(x|y) \\
 & =\sum_{x,y}P_{XY}(x,y) \log \frac{{P_{X|Y}(x|y)}}{P_{X}(x)} \\
 & =\sum_{x,y}P_{XY}(x,y) \log \frac{{P_{X|Y}(x|y)}P_{Y}(y)}{P_{X}(x)P_{Y}(y)} \\
 & =\sum_{x,y}P_{XY}(x,y) \log \frac{P_{XY}(x,y)}{P_{X}(x)P_{Y}(y)} \\
 & =D(P_{XY}||P_{X}P_{Y})
\end{align}
$$
3. $I(X;Y)\geq 0$

[[Mutual Information]]