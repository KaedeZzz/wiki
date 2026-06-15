---
source: "KaedeSync/_Knowledge/Mathematics/Probability Theory/Estimation and Inference/Monte Carlo/Importance Sampling.md"
ingested: 2026-06-09
---

We wish to estimate $I=\mathbb{E}_{p}\{f(X)\}=\int f(x)p(x)dx$
Another density $q(x)\neq{0}$ when $p(x)\neq 0$ is selected to be better aligned to the important regions, known as an *importance distribution*
Thus:
$$
\int f(x)p(x)dx=\int \frac{{f(x)p(x)}}{q(x)}q(x)dx=\mathbb{E}_{q}\left\{ \frac{f(x)p(x)}{q(x)} \right\}
$$
Monte Carlo estimate:
$$
\frac{1}{N}\sum_{n} \frac{{f(x_{n})p(x_{n})}}{q(x_{n})}
$$
with each $x_{n}\sim q(x)$.

**Intuitions**
To reduce variance and save computation, we do not waste effort in producing samples that do not contribute to the value of integral. The optimal importance density should approximate $q(x)\propto |f(x)|p(x)$.