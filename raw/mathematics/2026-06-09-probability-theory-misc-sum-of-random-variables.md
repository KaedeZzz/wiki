---
source: "KaedeSync/_Knowledge/Mathematics/Probability Theory/Misc/Sum of Random Variables.md"
ingested: 2026-06-09
---

Sum of Discrete [[Random Variable]]s:
Say $S=X+Y$,

$$ P_S(s)=\sum_{y\in\mathbb Y}P_{XY}(s-y,y)=\sum_{x\in\mathbb X}P_{XY}(x,s-x) $$

Sum of Continuous Variables:
Say $S=X+Y$,

$$ f_S(s)=\int_{-\infty}^{+\infty}f_{XY}(s-y,y)dy=\int_{-\infty}^{+\infty}f_{XY}(x,s-x)dx $$
If $X$ and $Y$ are independent, then:
$$
f_{S}(s)=\int_{-\infty}^{\infty}f_{X}(k)f_{Y}
(s-k)dk$$
therefore, the PDF of the sum of two variables with [[Independence]] is the convolution of their PDFs.