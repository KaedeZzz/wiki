---
source: KaedeSync/_Knowledge/Computer Vision/Features/Harrris Corner Detection Algorithm.md
ingested: 2026-07-06
---

We start with a smoothed image $S(x,y)$.
1. Calculate change in intensity in direction $\mathbf{n}$:
$$
\begin{align}
S_{n} & \equiv \nabla S(x,y)\cdot \hat{\mathbf{n}} \\
S_{n}^{2} & = \frac{{\mathbf{n}^{T}\nabla S\nabla S^{T}\mathbf{n}}}{\mathbf{n}^{T}\mathbf{n}}
\end{align}
$$
2. Smooth $S_{n}^{2}$ by convolution with a Gaussian kernel of size $\sigma_{I}$:
$$
\begin{align}
C_{n}(x,y) & =G_{\sigma_{I}}(x,y)*S_{n}^{2} \\
 & =\frac{{\mathbf{n}^{T}\begin{bmatrix}
\langle S_{x}^{2}\rangle & \langle S_{x}S_y\rangle \\
\langle S_{y}S_{x}\rangle & \langle S_{y}^{2}\rangle
\end{bmatrix}\mathbf{n}}}{\mathbf{n}^{T}\mathbf{n}}
\end{align}
$$
where $\langle\ \rangle$ is the smoothed value, and $S_{x}\equiv \partial S / \partial x$ and $S_{y}\equiv \partial S / \partial y$. 
This is equivalent to weighting the intensity differences squared, $S_{n}^{2}$, in the local neighborhood by Gaussian weights centered at $(x,y)$.
3. The smoothed intensity changes around $(x,y)$ gives a matrix of the form
$$
C_{n}(x,y)=\frac{\mathbf{n}^{T}\mathbf{An}}{\mathbf{n}^{T}\mathbf{n}}
$$
so the [[Elementary Eigenvector Theory]] tells that
$$
\lambda_{1}\leq C_{n}(x,y)\leq \lambda_{2}
$$
where $\lambda_{1}$ and $\lambda_{2}$ are the eigenvalues of $\mathbf{A}$. So, for every possible orientation $\mathbf{n}$, the maximum smoothed change in intensity is $\lambda_{2}$, and the minimum is $\lambda_{1}$.
4. We classify image structure around each pixel by looking at the eigenvalues of $\mathbf{A}$:
	- No structure: $\lambda_{1}\approx \lambda_{2}\approx 0$
	- Edge: $\lambda_{1}\approx 0$ (direction of edge), $\lambda_{2}$ large (normal to edge)
	- Corner: $\lambda_{1}$ and $\lambda_{2}$ large and distinct
5. In practice, we avoid computing the actual eigenvalues by evaluating the determinant ($\det \mathbf{A}=\lambda_{1}\lambda_{2}$) and trace ($\text{tr}\ \mathbf{A}=\lambda_{1}+\lambda_{2}$) instead. We mark corners where the quantity $\lambda_{1}\lambda_{2}-\kappa(\lambda_{1}+\lambda_{2})^{2}$ exceed some threshold.

[[Image Features]]