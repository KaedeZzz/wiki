---
source: "KaedeSync/_Knowledge/Mathematics/Probability Theory/Estimation and Inference/Monte Carlo/Sequential Importance Sampling.md"
ingested: 2026-06-09
---

For sequential [[Importance Sampling]], the target distribution is of the form
$$
\pi_{n}(x_{1: n})=\frac{{w_{n}(x_{1: n})q_{n}(x_{1: n})}}{Z_{n}}
$$
where
$$
w_{n}(x_{1: n})= \frac{\gamma_{n}(x_{1: n})}{q_{n}(x_{1: n})}
$$

is the importance weight, $\gamma$ is a measure function, and $Z$ the normalising constant.

We select an importance proposal density which has the following structure:
$$
\begin{align}
q_{n}(x_{1: n}) & =q_{n-1}(x_{1: n-1})q_{n}(x_{n}|x_{1: n-1}) \\
 & =q_{1}(x_{1})\prod_{k=2}^{n}q_{k}(x_{k}|x_{1: k-1}) 
\end{align}
$$
Practically, this means that to obtain particles $X_{1:n}^{i}\sim q_{n}(x_{1: n})$ at time $n$, we sample $X_{1}^{i}\sim q_{1}(x_{1})$ at time $1$ then $X_{k}^{i}\sim q_{k}(x_{k}|X_{1: k-1}^{i})$ at time $k$ for $k=2,\dots,n$. The associated un-normalised weights can be computed recursively using the decomposition
$$
w_{n}(x_{1: n})= \frac{\gamma_{n}(x_{1: n})}{q_{n}(x_{1: n})}=w_{n}(x_{1: n})= \frac{\gamma_{n-1}(x_{1: n-1})}{q_{n-1}(x_{1: n-1})} \frac{\gamma_{n}(x_{1: n})}{\gamma_{n-1}(x_{n-1})q_{n}(x_{n}|x_{1: n-1})}
$$
which can be written in the form
$$
w_{n}(x_{1: n})=w_{n-1}(x_{1: n-1})\alpha_{n}(x_{1: n})=w_{1}(x_{1})\prod_{k=2}^{n}\alpha_{k}(x_{1: k})
$$
where $\alpha$ is the *incremental importance weight* given by:
$$
\alpha_{n}(x_{1: n})= \frac{\gamma_{n}(x_{1: n})}{\gamma_{n-1}(x_{1: n-1})q_{n}(x_{n}|x_{1: n-1})}
$$
The sequential importance sampling is as follows:
- at time step 1, sample from proposal distribution, and compute weights $w_{1}$.
- at later timesteps, sample $X_{n}^{i}=q_{n}(x_{n}|X_{n-1}^{i})$, and compute weights
$$
w_{n}(X_{1: n}^{i})=w_{n-1}(X_{1: n-1}^{i})\cdot\alpha_{n}(X_{1: n}^{i})
$$

![[Resampling SMC]]

[[Sequential Monte Carlo]]