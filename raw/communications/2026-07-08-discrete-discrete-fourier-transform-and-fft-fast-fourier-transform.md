---
source: KaedeSync/_Knowledge/Communications/Discrete/Discrete Fourier Transform and FFT/Fast Fourier Transform.md
ingested: 2026-07-08
---

Perform the [[Discrete Fourier Transform]]
$$
\vec{X}=\mathbf{F}\vec{x}
$$
in $O(N\log N)$ instead of $O(N^{2})$ operations.

###### Algorithm
Assume the FFT length $N$ is not prime and can be factorised into two integers $N=ML$.
Reconsider a vector ($\vec{x} \text{ or }\vec{X}$) of length $N$ as an $L\times M$ array with $L$ rows and $M$ columns:

![[Pasted image 20241128135108.png]]

We usually use index $k$ for time domain vector $\vec{x}$, and index $n$ for frequency domain vector $\vec{X}$; we do 2-dimensional indexing into the array for those indices
$$
\begin{cases}
k=lM+s \\
n=mL+r
\end{cases}
$$
Then re-arrange the DFT:
$$
\begin{align}
X_{n}=X_{mL+r} & =\sum_{k=0}^{N-1}x_{k}W_{N}^{kn}=\sum_{s=0}^{M-1}\sum_{l=0}^{L-1}x_{lM+s}W_{N}^{(lM+s)(mL+r)} \\
 & =\sum_{s=0}^{M-1}\sum_{l=0}^{L-1}x_{lM+s}W_{N}^{lMmL}W_{N}^{lMr}W_{N}^{smL}W_{N}^{sr} \\
 & =\sum_{s=0}^{M-1}W_{M}^{sm}W_{N}^{sr}\sum_{l=0}^{L-1}x_{lM+s}W_{L}^{rl}
\end{align}
$$
where we have used the following:
$$
\begin{align}
 W_{N}^{lmML} & =W_{N}^{lmN}=1 \\
 W_{N}^{L}  & =W_M \\
 W_{N}^{M}  & =W_L
\end{align}
$$
because $e^{-j 2\pi L/N}=e^{-j{2}\pi/M}$ and etc.

The obtained expression divides the $N$-point DFT into 3 steps:

![[Pasted image 20241128135943.png]]

1. Take the $L$-point DFT of every column ($M$ times), $LM^{2}$ multiplications. (note that we do not need to repeatedly calculate this for different $X_{mL+r}$)
2. Multiply every element by its twiddle factor, $N=LM$ multiplications
3. Take the $M$-point DFT of every row ($L$ times), $L^{2}M$ multiplications

Total number of operations is then $ML(1+M+L)$.

![[Radix-2 FFT]]