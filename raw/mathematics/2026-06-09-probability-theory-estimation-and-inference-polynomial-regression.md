---
source: "KaedeSync/_Knowledge/Mathematics/Probability Theory/Estimation and Inference/Polynomial Regression.md"
ingested: 2026-06-09
---

Task: fit data with a polynomial
$$
f_{w}(x)=w_{0}+w_{1}x+w_{2}x^{2}+\dots+w_{N}x^{M}
$$
where $w_{j}$ are the weights/parameters.
Optimal parameters minimize sum of squared errors $\sum_{i}e_{i}^{2}=\sum_{i}(y_{i}-f(x_{i}))^{2}$.
In matrix form, the error:
$$
E(\mathbf{w})=\mathbf{e}^{T}\mathbf{e}=(\mathbf{y}-\mathbf{f})^{T}(\mathbf{y}-\mathbf{f})
$$
and the function:
$$
\begin{align}
f_{w}(x) & =\sum_{j=0}^{M}w_{j}\phi_{j}(x)\text{ where }\phi_{j}(x)\text{ are basis functions} \\
\mathbf{\Phi}_{ij} & =\phi_{j}(x_{i})\text{ allows us to write }\mathbf{f}=\mathbf{\Phi w}
\end{align}
$$
**The fact that the model can be expressed as $\mathbf{f}=\mathbf{\Phi w}$ defines linear model.**
Therefore:
$$
\begin{align}
E(\mathbf{w}) & =(\mathbf{y}-\mathbf{\Phi w})^{T}(\mathbf{y}-\mathbf{\Phi w}) \\
\frac{\partial E(\mathbf{w})}{\partial \mathbf{w}} & =-2\Phi^{T}(\mathbf{y}-\mathbf{\Phi w})=\mathbf{0}\implies  \hat{\mathbf{w}}=(\mathbf{\Phi}^{T}\mathbf{\Phi })^{-1}\mathbf{\Phi}^{T}\mathbf{y}
\end{align}
$$
Geometrical view:
- the vector of training targets $\mathbf{y}$ lives in a $N$-dimensional vector space. where $N$ is the number of parameters.
- we try to make $\mathbf{f}$ as close (in terms of $I_{2}$-norm, that is, sum of error square) as possible to $\mathbf{y}$, but $\mathbf{f}$ is constrained on column space of $\mathbf{\Phi}$.
- As a result, the optimal vector $\hat{\mathbf{f}}$ is the projection of $\mathbf{y}$ on column space, that is, $\hat{\mathbf{f}}=\mathbf{\Phi w}=\mathbf{\Phi}(\mathbf{\Phi}^{T}\mathbf{\Phi})^{-1}\mathbf{\Phi}^{T}\mathbf{y}$ (note the column space projection form).
- Consequently, the residual vector $\mathbf{e}$ lies in left nullspace of $\mathbf{\Phi}$, i.e. $\mathbf{\Phi}^{T}\mathbf{e}=\mathbf{0}$.

Likelihood of data, considering noise:

![[Likelihood]]

Assume that the data noise is distributed i.i.d. as
$$
p(\epsilon_{n})=\frac{1}{\sqrt{ 2\pi\sigma ^{2} }}\exp\left( - \frac{\epsilon_{n}^{2}}{2\sigma ^{2}_{noise}} \right)
$$
vector notation:
$$
\mathbf{\epsilon}\sim\mathcal N(\mathbf{0},\sigma ^{2}_{noise}\mathbf{I})
$$
since $\mathbf{y}=\mathbf{\Phi w}+\mathbf{\epsilon}$, we can write likelihood as
$$
\mathbf{y}\sim\mathcal N(\mathbf{\Phi w},\sigma ^{2}_{noise})
$$
and we fit the model weights to the data by maximising the likelihood
$$
\hat{\mathbf{w}}=\arg\max \exp\left( - \frac{\epsilon^{T}\epsilon}{2\sigma^{2}_{noise}} \right)=\arg\min E(\mathbf{w})
$$
