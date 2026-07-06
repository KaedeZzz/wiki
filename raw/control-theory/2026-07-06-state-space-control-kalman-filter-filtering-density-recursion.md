---
source: KaedeSync/_Knowledge/Control Theory/State-Space Control/Kalman Filter/Filtering Density Recursion.md
ingested: 2026-07-06
---

We obtain the [[Filtering Density]] from [[Bayes Theorem]]:
$$
p(x_{t}|y_{1: t})\propto p(y_{t}|x_{t})\int p(x_{t}|x_{t-1})p(x_{t-1}|y_{1: t-1})dx_{t-1}
$$
which has two steps:
1. Prediction step
$$
p(x_{t}|y_{1: t-1})=\int p(x_{t}|x_{t-1})p(x_{t-1}|y_{1: t-1})dx_{t-1}
$$
2. Update
$$
p(x_{t}|y_{1: t})\propto p(y_{t}|x_{t})p(x_{t}|y_{1: t-1})
$$
