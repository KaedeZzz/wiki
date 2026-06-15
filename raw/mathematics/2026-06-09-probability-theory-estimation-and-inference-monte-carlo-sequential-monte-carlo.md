---
source: "KaedeSync/_Knowledge/Mathematics/Probability Theory/Estimation and Inference/Monte Carlo/Sequential Monte Carlo.md"
ingested: 2026-06-09
---

Sequential [[Monte Carlo]] (SMC) methods are a general class of Monte Carlo methods that sample sequentially from a sequence of target probability densities $\{ \pi_{n}(x_{1: n}) \}$ *of increasing dimension* where each distribution $\pi_{n}(x_{1: n})$ is defined on the product space $\mathcal{X}^{n}$. Writing
$$
\pi_{n}(x_{1: n})= \frac{\gamma_{n}(x_{1: n})}{Z}
$$
we only require that $\gamma_{n}:\mathcal{X}^{n}\to \mathbb{R}^{+}$ is known pointwise; the normalising constant can be unknown. SMC provides an approximation of $\pi_{1},Z_{1}$ at time $1$ and $\pi_{2},Z_{2}$ at time $2$ and so on.

[[State-space Model]]

