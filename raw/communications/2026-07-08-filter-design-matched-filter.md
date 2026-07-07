---
source: KaedeSync/_Knowledge/Communications/Filter Design/Matched Filter.md
ingested: 2026-07-08
---

Matched filter describes the task of detecting a known deterministic signal $s_{n}, n=0,...,n-1$ buried in random noise $v_{n}$:
$$
x_{n}=s_{n}+v_{n}
$$
Formulation of the problem:
$$
\mathbf{x}=\mathbf{s}+\mathbf{v}
$$
the output of the filter at time $N-1$ is:
$$
y_{N-1}=\sum_{m=0}^{N-1}h_{m}x_{N-1-m}=\mathbf{h}^{T}\tilde{\mathbf{x}}=\mathbf{h}^{T}(\tilde{\mathbf{s}}+\tilde{\mathbf{v}})=y^{s}_{N-1}+y^{n}_{N-1}
$$
where $\tilde{\mathbf{x}}$ (vector with the tilde sign) is the "time-reversed" vector.

We attempt to **maximise the output [[Signal-to-Noise Ratio (SNR)]]** which is defined as
$$
\frac{\mathbb{E}[|y^{s}_{N-1}|^{2}]}{\mathbb{E}[|y^{n}_{N-1}|^{2}]}=\frac{\mathbb{E}[|\mathbf{h}^{T}\tilde{\mathbf{s}}|^{2}]}{\mathbb{E}[|\mathbf{h}^{T}\tilde{\mathbf{v}}|^{2}]}=\frac{|\mathbf{h}^{T}\tilde{\mathbf{s}}|^{2}}{\mathbb{E}[|\mathbf{h}^{T}\tilde{\mathbf{v}}|^{2}]}
$$
(since numerator is not a random quantity.)

**Energy of signal component**
$$|\mathbf{h}^{T}\tilde{\mathbf{s}}|^{2}=(\mathbf{h}^{T}\tilde{\mathbf{s}})(\tilde{\mathbf{s}}^{T}\mathbf{h})=\mathbf{h}^{T}(\tilde{\mathbf{s}}\tilde{\mathbf{s}}^{T})\mathbf{h}$$
to analyse, consider the matrix $\mathbf{M}=\mathbf{\tilde{s}\tilde{s}}^{T}$. What is its [[Eigenvalue and Eigenvector]]? Note that
$$
(\mathbf{\tilde{s}\tilde{s}}^{T})\mathbf{\tilde{s}}=\mathbf{\tilde{s}}\underbrace{(\mathbf{\tilde{s}}^{T}\mathbf{\tilde{s}})}_{\text{scalar}}=(\mathbf{\tilde{s}}^{T}\mathbf{\tilde{s}})\mathbf{\tilde{s}}
$$
Hence the (normalised) vector $\mathbf{e}_{0}=\frac{\mathbf{\tilde{s}}}{\lvert \mathbf{\tilde{s}} \rvert}$ is an eigenvector of the matrix $\mathbf{M}$ and its eigenvalue is $\mathbf{\tilde{s}}^{T}\mathbf{\tilde{s}}$.
Additionally, it is obvious that any vector perpendicular to $\mathbf{e}_{0}$ is also an eigenvector with eigenvalue $0$. We can construct a set of $N-1$ orthonormal eigenvectors with eigenvalue $0$ that completes the set of $N$ eigenvectors. Thus we can express
$$
\begin{align}
\mathbf{Mh} & =\mathbf{M}(\alpha \mathbf{e}_{0}+\beta \mathbf{e}_{1}+\dots) \\
 & =\alpha\mathbf{Me}_{0} \\
 & =\alpha(\mathbf{\tilde{s}}^{T}\mathbf{\tilde{s}})\mathbf{e}_{0} \\
\mathbf{h}^{T}(\mathbf{\tilde{s}}\mathbf{\tilde{s}}^{T})\mathbf{h} & =\alpha(\mathbf{\tilde{s}}^{T}\mathbf{\tilde{s}})\mathbf{h}^{T}\mathbf{e}_{0} \\
 & =\alpha(\mathbf{\tilde{s}}^{T}\mathbf{\tilde{s}})(\alpha \mathbf{e}_{0}^{T}+\beta \mathbf{e}_{1}^{T}+\dots)\mathbf{e}_{0} \\
 & =\alpha ^{2}(\mathbf{\tilde{s}}^{T}\mathbf{\tilde{s}})
\end{align}
$$

**Energy of noise component**
$$
\mathbb{E}[\lvert \mathbf{h}^{T}\mathbf{\tilde{v}} \rvert^{2} ]=\mathbf{h}^{T}\mathbb{E}[\mathbf{\tilde{v}}^{T}\mathbf{\tilde{v}}]\mathbf{h}
$$
Assume the noise signal being [[White Noise]]:
$$
\mathbb{E}[v_{i}v_{j}]=
\begin{cases}
\sigma_{v}^{2},\quad  & i=j \\
0,\quad  & i\neq j
\end{cases}
$$
Therefore:
$$
\begin{align}
\mathbb{E}[\mathbf{\tilde{v}}^{T}\mathbf{\tilde{v}}] & =\sigma_{v}^{2}\mathbf{I} \\
\mathbb{E}[\lvert \mathbf{h}^{T}\mathbf{\tilde{v}} \rvert^{2} ] & =\sigma_{v}^{2}\mathbf{h}^{T}\mathbf{h}=\sigma_{v}^{2}(\alpha ^{2}+\beta ^{2}+\dots)
\end{align}
$$

Wrapping up SNR, we have
$$
\text{SNR}=\frac{{\alpha ^{2}\mathbf{\tilde{s}}^{T}\mathbf{\tilde{s}}}}{\sigma_{v}^{2}(\alpha ^{2}+\beta ^{2}+\dots)}
$$
Clearly scaling $\mathbf{h}$ by some factor does not change the SNR, so we can analyse SNR by arbitrarily fixing $\lvert \mathbf{h} \rvert=1$ and then maximise it. In this case, SNR becomes
$$
\text{SNR}=\frac{\alpha ^{2}}{\sigma_{v}^{2}}\mathbf{\tilde{s}}^{T}\mathbf{\tilde{s}}
$$
Obviously the largest possible value of $\alpha$ giving $\lvert \mathbf{h} \rvert=1$ is $\alpha=1$ and $\beta=\gamma=\dots=0$. This gives
$$
\mathbf{h}_{opt}=\mathbf{e}_{0}=\frac{\mathbf{\tilde{s}}}{\lvert \mathbf{\tilde{s}} \rvert }\quad \text{and}\quad \text{SNR}_{opt}=\frac{\mathbf{\tilde{s}}^{T}\mathbf{\tilde{s}}}{\sigma_{v}^{2}}
$$
and clearly the performance (as expected) very much depends on the energy of the signal $s$ and noise $v$.