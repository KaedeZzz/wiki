---
source: KaedeSync/_Knowledge/Communications/Filter Design/Wiener Filter.md
ingested: 2026-07-08
---

General Wiener filter problem:
- A desired signal $d_{n}$ is observed in noise $v_{n}$: $x_{n}=d_{n}+v_{n}$
- Wiener showed how to design a linear filter which would optimally estimate $d_{n}$ given just the noisy observations $x_{n}$ and some fundamental assumptions about the statistics of the signal.

In the most general case, we can filter the observed signal $x_{n}$ with an infinite dimensional filter, having a non-causal impulse response $h_{p}$:
$$
\{ h_{p};p=-\infty, \dots,-1,0,1,2,\dots,\infty \}
$$
We then filter the observed noisy signal using the filter $\{ h_{p} \}$ to obtain an estimate $\hat{d}_{n}$ of the desired signal:
$$
\hat{d}_{n}=\sum_{p=-\infty}^{\infty}h_{p}x_{n-p}
$$
Error signal:
$$
\epsilon_{n}=d_{n}-\hat{d}_{n}=d_{n}-\sum_{p=-\infty}^{\infty}h_{p}x_{n-p}
$$

The mean-squared error is then defined as:

![[Mean Squared Error]]

The Wiener filter minimises $J$ with respect to the filter coefficients $\{ h_{p} \}$.


###### Derivation of the filter
The Wiener filter assumes that $\{ x_{n} \}$ and $\{ d_{n} \}$ are jointly wide-sense stationary, which means that both processes have constant mean (which is assumed zero specifically for Wiener filter), and all [[Autocorrelation]] and cross correlation functions depend only on the time differences.

Minimising expected error w.r.t. impulse response values:
$$
\frac{{\partial J}}{\partial h_{q}}=\frac{{\partial \mathbb{E}[\epsilon_{n}^{2}]}}{\partial h_{q}}=\mathbb{E}[\frac{{\partial\epsilon_{n}^{2}}}{\partial h_{q}}]=\mathbb{E}[2\epsilon_{n}\frac{{\partial\epsilon_{n}}}{\partial h_{q}}]=0
$$
simultaneously for all $q \in \{ -\infty, \dots,-1,0,1, \dots,\infty \}$ 
The term $\frac{{\partial\epsilon_{n}}}{\partial h_{q}}$ is calculated as:
$$
\frac{{\partial\epsilon_{n}}}{\partial h_{q}}=\frac{{\partial}}{\partial h_{q}}\left\{  d_{n}-\sum_{p=-\infty}^{\infty}h_{p}x_{n-p}  \right\}=-x_{n-q}
$$
Therefore,
$$
\mathbb{E}[2\epsilon_{n}\frac{{\partial\epsilon_{n}}}{\partial h_{q}}]=-2\mathbb{E}[\epsilon_{n}x_{n-q}]=0\quad \text{for all }q
$$
This is known as the orthogonality principle.

Substitution for $\epsilon_{n}$ gives
$$
\begin{align}
\mathbb{E}[\epsilon_{n}x_{n-q}] & =\mathbb{E}\left[\left(  d_{n}-\sum_{p=-\infty}^{\infty}h_{p}x_{n-p}\right)x_{n-q}\right] \\
 & =\mathbb{E}[d_{n}x_{n-q}]-\sum_{p=-\infty}^{\infty}h_{p}\mathbb{E}[x_{n-q}x_{n-p}] \\
 & =r_{xd}[q]-\sum_{p=-\infty}^{\infty}h_{p}r_{x x}[q-p]=0
\end{align}
$$
Hence the solution must satisfy
$$
\sum_{p=-\infty}^{\infty}h_{p}r_{XX}[q-p]=r_{xd}[q]
$$
which is known as [[Wiener-Hopf Equations]].
Now:
$$
h_{q}*r_{x x}[q]=r_{xd}[q]
$$
Re-write in frequency domain:
$$
\begin{align}
H(e^{j\Omega})S_{x}(e^{j\Omega}) & =S_{xd}(e^{j\Omega}) \\
H(e^{j\Omega}) & = \frac{S_{xd}(e^{j\Omega})}{S_{x}(e^{j\Omega})}
\end{align}
$$
Expected MSE:
$$
J_{\min}=\mathbb{E}[\epsilon_{n}d_{n}]=r_{dd}[0]-\sum_{p=-\infty}^{\infty}h_{p}r_{xd}[p]
$$
#TBD

[[Optimal Filtering]]