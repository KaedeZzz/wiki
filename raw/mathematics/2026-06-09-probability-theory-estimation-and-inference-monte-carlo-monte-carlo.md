---
source: "KaedeSync/_Knowledge/Mathematics/Probability Theory/Estimation and Inference/Monte Carlo/Monte Carlo.md"
ingested: 2026-06-09
---

We can approximate integrals of the form
$$
\mathbf{z}=\int f(x)p(x)dx
$$
where $p(x)$ is a probability distribution, using a sum
$$
\mathbf{z}\approx \frac{1}{T}\sum_{t=1}^{T}f(x^{(t)})\text{ where }x^{(t)}\sim p(x)
$$
As $T\to \infty$ the approximation converges to true integral.