---
source: KaedeSync/_Knowledge/Communications/Discrete/Discrete Fourier Transform and FFT/Inverse DFT.md
ingested: 2026-07-08
---

$$
\mathbf{F}^{-1}=\frac{1}{N}\mathbf{F}^{*} \text{ because } \frac{1}{N}\mathbf{FF}^{*}=\mathbf{I}_{N}
$$
where $\mathbf{I}_{N}$ denotes an identity matrix of size $N$.

Since $(W_{N}^{k})^{*}=W_{N}^{N-k}$, the inverse DFT matrix $\mathbf{F}^{-1}$ has:
- the same row $0$ as $\mathbf{F}$ and 
- rows $1$ to $N-1$ are corresponding rows of $\mathbf{F}$ in reverse order, counting down from $N-1$ to $1$.

