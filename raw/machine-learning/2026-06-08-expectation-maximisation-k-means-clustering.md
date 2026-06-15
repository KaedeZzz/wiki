---
source: KaedeSync/_Knowledge/Machine Learning/Expectation-Maximisation/K-means Clustering.md
ingested: 2026-06-08
---

The K-means algorithm is an algorithm for putting $N$ data points in an $I$-dimensional space into $K$ clusters, where each cluster is parameterised by a vector $\mathbf{m}^{(k)}$ called its mean.

###### Process

To start the K-means algorithm, the means are initialised in some way.

It is an iterative two step algorithm.
In the *assignment* step, each data point $n$ is assigned to the nearest mean.
In the *update* step, the means are adjusted to match the sample means of the data points that they are responsible for.

The algorithm is guaranteed to converge to a

###### Algorithm

**Initialisation**
Set $K$ means $\{ \mathbf{m}^{(k)} \}$ to random values.

**Assignment Step**
Each data point $n$ is assigned to the nearest mean. We denote our guess for the cluster $k^{(n)}$ that the point $\mathbf{x}^{(n)}$ belongs to by $\hat{k}^{(n)}$. In the assignment step, we set "responsibility" indicator variable $r_{k}^{(n)}$ by:
$$
r_{k}^{(n)}=
\begin{cases}
1\quad \text{if}\quad \hat{k}^{(n)}=k \\
0\quad \text{if}\quad \hat{k}^{(n)}\neq k
\end{cases}
$$

**Update Step**
The model parameters, the means, are adjusted to match the sample means of the data points that they are responsible for:
$$
\mathbf{m}^{(k)}=\frac{{\sum_{n}r_{k}^{(n)}\mathbf{x}^{(n)}}}{\sum_{n}r_{k}^{(n)}}
$$

Repeat until the assignments do not change.

###### Further Discussion

The algorithm has no way of representing the size or shape of a cluster; for some certain shapes of distributions of data it might "fail".
