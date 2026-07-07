---
source: KaedeSync/_Knowledge/Information Theory/Basics/Differential Entropy.md
ingested: 2026-07-06
---

The differential entropy of a continuous random variable $X$ with PDF $f_{X}$ is:

$$
h(X)=\int_{-\infty}^{\infty}f_{X}(u)\log \frac{1}{f_{X}(u)}du
$$

The differential entropy $h(X)$ can be interpreted as the uncertainty of  a continuous random variable $f_{X}$ relative to the uncertainty of a $\text{Unif}[0,1]$ variable (which is a baseline and has $0$ differential entropy).

[[Information Theory]], [[Information Entropy]]
