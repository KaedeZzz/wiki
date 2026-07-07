---
source: KaedeSync/_Knowledge/Communications/Discrete/Discrete Fourier Transform and FFT/DFT Matrix.md
ingested: 2026-07-08
---

We can re-write the DFT as a matrix-vector operation:
$$
\begin{bmatrix}
X_{0} \\
X_{1} \\
X_{2} \\
\vdots \\
X_{N-1}
\end{bmatrix}
=
\begin{bmatrix}
1 & 1 & \dots & 1 \\
1 & e^{-j\frac{2\pi}N} & \dots  & e^{-j\frac{2\pi}N(N-1)} \\
1 & e^{-j\frac{2\pi}N 2} & \dots & e^{-j\frac{2\pi}N 2(N-1)} \\
\vdots & \vdots &  & \vdots \\
1 & e^{-j\frac{2\pi}N (N-1)} & \dots & e^{-j\frac{2\pi}N {(N-1)}^{2}}
\end{bmatrix}
\begin{bmatrix}
x_{0} \\
x_{1} \\
x_{2} \\
\vdots \\
x_{N-1}
\end{bmatrix}
$$
Let us define $W_{N}=e^{-j\frac{2\pi}N}$, then the DFT matrix becomes:
$$
\mathbf{F}=\begin{bmatrix}
1 & 1 & 1 & \dots & 1 \\
1 & W_{N} & W_{N}^{2} & \dots & W_{N}^{N-1} \\
1 & W_{N}^{2} & W_{N}^{4} & \dots & W_{N}^{2(N-1)} \\
\vdots & \vdots& \vdots &  & \vdots  \\
1 & W_{N}^{N-1} & W_{N}^{2(N-1)} & \dots & W_{N}^{(N-1)^{2}}
\end{bmatrix}
$$

This is known as a [[Vandermonde]] matrix with parameters $1,W_{N},W_{N}^{2},\dots,W_{N}^{N-1}$.

$W_{N}$ is called **primitive $N$-th root of unity**

Properties of $W_{N}=e^{-j\frac{2\pi}N}$:
- None of the powers $1,2,\dots,N-1$ of $W_{N}$ equal to 1, but the $N$-th power equal to 1. This allows us to re-write $\mathbf{F}$ with powers of $W_{N}$ within $0$ and $N-1$.
- $(W_{N}^{k})^{*}=(e^{-j 2\pi k/N})^{*}=e^{j{2}\pi k/N}=W_{N}^{-k}=W_{N}^{N-k}$
- Every row except row $0$ sum to $0$: all the primitive roots are points evenly spaced on a unit circle so they must sum to $0$. Same applies for columns: for all columns, $\vec{f}_{l}\cdot\vec{f}_{m}=0\text{ for }l\neq m,\vec{f}_{l}\cdot\vec{f}_{l}=N$ 
- Therefore, DFT an **orthogonal basis transform**

![[Inverse DFT]]


![[Cyclic Properties of DFT Matrix 1]]