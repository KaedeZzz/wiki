---
source: "KaedeSync/_Knowledge/Mathematics/Probability Theory/Basics/Bivariate.md"
ingested: 2026-06-09
---

Bivariate are two jointly distributed random variables.

joint PMF:
$$
p_{X,Y}(x_{i}, y_{i})=P(X=x_{i}, y=y_{i})
$$

marginal PMF:
$$
p_{X}(x_{k})=\sum_{i=1}^np_{X,Y}(x_{k},y_{i})
$$

conditional PMF: 
$$
p_{X|Y}(x_{i},y_{i})=\frac{p_{XY}(x_{i},y_{i})}{p_{Y}(y_{i})}
$$