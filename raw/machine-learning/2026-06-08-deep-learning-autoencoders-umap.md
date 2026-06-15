---
source: KaedeSync/_Knowledge/Machine Learning/Deep Learning/Autoencoders/UMAP.md
ingested: 2026-06-08
---

**Uniform Manifold Approximation and Projection (2018)**
[[UMAP; Uniform Manifold Approximation and Projection for Dimension Reduction, McInnes et al. (2020)]]

Core idea: check distances in high dimensional space and remain similarity in low dimensional space, like SNE.
Instead of using probability distributions, it uses **graph**.

Method:
1. find [[k-nearest Neighbours]]. $k$ is the major hyperparameter of UMAP.
2. For each point, transform its connections to neighbours to a weighted graph: $$
v_{i,j}=\exp \left\{  - \frac{\max(0, d(x_{i},x_{j})-\rho_{i})}{\sigma_{i}}  \right\}
$$ $\rho_{i} =$ distance to nearest neighbour. No need to standardise; computation is thus faster.
3. Combine all graphs. $$
w_{ij}=v_{i,j}+v_{j,i}-v_{i,j}\cdot v_{j,i}
$$Since $v_{i,j}$ is between 0 and 1, the combined weight is also between 0 an 1. Therefore graph representation in high dimension is done.
4. Repeat process in low dimension.
5. Use [[Loss Function]] to evaluate similarity: compare [[Cross Entropy]] of the two adjacency matrices of two graphs and use [[Gradient Descent]] to minimise the loss and change low dimension representation accordingly. $$
\text{Loss}=\sum w_{hd}(i,j)\log\left( \frac{w_{hd}(i,j)}{w_{ld}(i,j)}\right)+\sum (1-w_{hd}(i,j))\log\left( \frac{1-w_{hd}(i,j)}{1-w_{ld}(i,j)}\right)
$$

Faster than t-SNE but slower than PCA.
Very high quality. Good at keeping relative positions.
![[Pasted image 20240912221034.png]]
Increasing number of nearest neighbours make the behaviour of model more predictable (better latent space).
Perplexity: not sure increase of perplexity really helped.
