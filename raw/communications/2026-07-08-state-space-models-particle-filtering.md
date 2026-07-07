---
source: KaedeSync/_Knowledge/Communications/State-Space Models/Particle Filtering.md
ingested: 2026-07-08
---

We attempt to recursively obtain the filtering density with [[Sequential Monte Carlo]] samples.

![[Filtering Density Recursion]]

We attempt to mimic the recursion steps by Monte Carlo operations.

First, consider the simplest case in which $\gamma_{n}(x_{1: n})=p(x_{1: n},y_{1: n})$ is chosen, yielding $\pi_{n}(x_{1: n})=p(x_{1: n}|y_{1: n})$. In order to select the optimal proposal density, we select one that yields minimal variance of the importance weights, that is,
$$
q^{opt}(x_{n}|x_{1: n-1})=\pi_{n}(x_{n}|x_{1: n-1})=\frac{g(y_{n}|x_{n})f(x_{n}|x_{n-1})}{p(y_{n}|x_{n-1})}
$$
In many scenarios, we cannot sample from this distribution, so we should aim to approximate it; in any case, though, it shows that we should use an importance distribution of the form
$$
q_{n}(x_{n}|x_{1: n-1})=q(x_{n}|y_{n},x_{n-1})
$$

For [[Bootstrap Particle Filter]], simply make $qq(x_{n}|y_{n},x_{n-1})=p(x_{n}|x_{n-1})$.

**Particle Filter Algorithm**
**Step 1. Prediction**
To use the existing point cloud to sample new cloud that represents states, we simply sample each particle using the state transition probability:
$$
x_{t}(i)\sim p(x_{t}|x_{t-1}^{(i)})
$$
this gives a predicted cloud representing $p(x_{t}|y_{1: t-1})$.

**Step 2. Update**
At time $t$, we want the posterior filtering distribution $p(x_{t}|y_{1: t})$, but we have samples from a proposal distribution $p(x_{t}|y_{1: t-1})$. Using [[Bayes Theorem]], we find out that:
$$
p(x_{t}|y_{1: t})\propto p(y_{t}|x_{t})p(x_{t}|x_{t-1})p(x_{t-1}|p_{1: t-1})
$$
for Bootstrap filters, let the weight be
$$
\tilde{w}_{t}^{(i)}=w_{t-1}^{(i)}p(y_{t}|x_{t}^{(i)})
$$
then normalise:
$$
w_{t}^{(i)}=\frac{{\tilde{w}_{t}^{(i)}}}{\sum_{j=1}^{N}\tilde{w}_{t}^{(j)}}
$$
Step 3. Resampling (avoid particle collapse)
After many steps, most particles will have tiny weights expect few, which is known as particle degeneracy. We detect it using effective sample size:
$$
ESS = \frac{1}{\sum_{i}(w_{t}^{(i)})^{2}}
$$
if $ESS<N / 2$ (common threshold), we resample:
- draw $N$ new particles from the current set with probability proportional to $w_{t}^{(i)}$
- reset all weights to $\frac{1}{N}$

This focuses computation on plausible state regions.