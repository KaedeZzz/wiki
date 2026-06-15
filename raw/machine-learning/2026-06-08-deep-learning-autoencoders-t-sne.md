---
source: KaedeSync/_Knowledge/Machine Learning/Deep Learning/Autoencoders/t-SNE.md
ingested: 2026-06-08
---

**t-Distributed Stochastic Neighbour Embedding (2008)**

**SNE: Stochastic Neighbour Embedding**
Main idea: points that are close in high dimension space should also be close in low dimension space
Use a special [[Loss Function]] to describe difference between high dimension expression and low dimension expression, then minimize it
$$
\frac{\partial\text{Loss}(\text{HighDim},\text{LowDim})}{\partial\text{LowDim}}=0
$$
Practical calculation:
1. In high dimension space $\mathbb{X}$, convert distance between a point to other points _probablistically_ into a [[Gaussian Distribution]]$$
p_{0,j}=\exp\left(- \frac{||x_{0}-x_{j}||^{2}}{2\sigma_{0}^{2}}\right)
$$To practically standardise the probabilities (such that they sum to 1): [[Softmax Function]].$$
p_{i,j}=\frac{\exp\left(- \frac{||x_{i}-x_{j}||^{2}}{2\sigma_{i}^{2}}\right)}{\sum_{k\neq i}\exp\left(- \frac{||x_{i}-x_{k}||^{2}}{2\sigma_{i}^{2}}\right)}
$$ (computationally expensive)
2. In low dimension space $\mathbb{Y}$, randomly put points, then calculate probabilities $$
q_{i,k}=\frac{\exp\left(- {||y_{i}-y_{j}||^{2}}\right)}{\sum_{k\neq i}\exp\left(- {||y_{i}-y_{k}||^{2}}\right)}
$$
3. Use [[KL Divergence]] to evaluate their similarities. $$
D_{KL}(P||Q)=\sum_{i}\sum_{j}p_{i,j}\log \frac{p_{i,j}}{q_{i,j}}
$$ $$
\frac{\partial D_{KL}(P||Q)}{\partial y_{i}}=2\sum_{j}(p_{i,j}-q_{i,j}+p_{j,i}-q_{j,i})(y_{i}-y_{j})
$$

How to decide $\sigma_{i}$? 
Iteratively try different $\sigma$ until the [[Perplexity]] matches hyperparameter value
*Note that effect of value of perplexity on clusters in latent space is not straightforward; repetitive testing is required to select a best perplexity. Changing perplexity even slightly would greatly change latent space visualisation.*
The larger the perplexity is, the larger the computational cost is.

Pros: non-linear
Cons: SLOW

**t-SNE**
Use [[Gaussian Distribution]] in high dimensional space and [[Student's t-distribution]] in low dimensional space.
Still much slower than PCA.
