---
source: KaedeSync/_Knowledge/Communications/Discrete/Discrete Fourier Transform and FFT/Einstein-Wiener-Kitchin Theorem Explained.md
ingested: 2026-07-08
---

![[Einstein-Wiener-Kitchin Theorem]]

Take a time-windowed version of ta signal $x_{n}$, having duration $2N+1$ samples and zero elsewhere:
$$
x_{n}^{N}=w_{n}^{N}x_{n}
$$
where
$$
w_{n}^{N}=
\begin{cases}
1, \quad  & -N\leq n\leq N \\
0, \quad  & \text{otherwise}
\end{cases}
$$
The [[Discrete-time Fourier Transform (DTFT)]] is:
$$
X^{N}(e^{j\Omega})=\sum_{n=-\infty}^{+\infty}w_{n}^{N}x_{n}e^{-jn\Omega}
$$
Its modulus squared:
$$
\lvert X^{N}(e^{j\Omega}) \rvert ^{2}=X^{N}(e^{j\Omega})X^{N}(e^{j\Omega})^{*}
$$
and hence we can write the following DTFT pair that
$$
\text{DTFT}\{ x_{n}^{N}*x_{-n}^{N} \}=X^{N}(e^{j\Omega})X^{N}(e^{j\Omega})^{*}=\lvert X^{N}(e^{j\Omega}) \rvert ^{2}
$$
where $x_{-n}^{N}$ is the time-reversed version of $x_{n}^{N}$. 
Now expand the time-domain convolution:
$$
x_{n}^{N}*x_{-n}^{N}=\sum_{n=-\infty}^{+\infty}x_{n}^{N}x_{n-m}^{N}=\sum_{n=-\infty}^{+\infty}x_{n}w_{n}x_{n-m}w_{n-m}
$$
so we have
$$
\text{DTFT}\{\sum_{n=-\infty}^{+\infty}x_{n}w_{n}x_{n-m}w_{n-m}\}=\lvert X^{N}(e^{j\Omega}) \rvert ^{2}
$$
Multiply both sides and take expectation:
$$
\text{DTFT}\left\{  \mathbb{E}\left[ \frac{1}{2N+1}(\sum_{n=-\infty}^{+\infty}x_{n}w_{n}x_{n-m}w_{n-m}) \right]  \right\}=\text{DTFT}\left\{  \mathbb{E}\left[ \frac{1}{2N+1}\lvert X^{N}(e^{j\Omega}) \rvert ^{2} \right]  \right\}
$$
But notice that, for [[Wide-Sense Stationary]] process $\{ x_{n} \}$, we have
$$
\begin{align}
\mathbb{E}\left[ \frac{1}{2N+1}\left( \sum_{n=-\infty}^{+\infty}x_{n}w_{n}x_{n-m}w_{n-m} \right) \right] & = \frac{1}{2N+1}\sum_{n=-\infty}^{+\infty}r_{xx}[m]w_{n}w_{n-m}  \\
 & =r_{xx}[m]\left(\frac{1}{2N+1}\sum_{n=-\infty}^{+\infty}w_{n}w_{n-m}\right)   \\
 & =r_{xx}[m]\cdot t[m]
\end{align}
$$
where $t[m]$ is a deterministic [[Autocorrelation]] function of the window function:

![[Pasted image 20250113103106.png]]

To summarise, we have obtained the relationship
$$
\text{DTFT}\{ r_{xx}[m]t[m] \}=S_{x}(e^{j\Omega})*T(e^{j\Omega})=\mathbb{E}\left[ \frac{1}{2N+1} \lvert X^{N}(e^{j\Omega}) \rvert^{2} \right]
$$
Notice that, as the window width $N$ increases, $t[m]$ gets "wider and flatter" $T(e^{j\Omega})$ tends more to a delta function:
![[Pasted image 20250113103612.png]]
Therefore:
$$
\begin{align}
\lim_{ N \to \infty } \text{DTFT}\{ r_{xx}[m]t[m] \}=\text{DTFT}\{ r_{xx}[m] \} & =S_{x}(e^{j\Omega}) \\
 & =\lim_{ N \to \infty }\mathbb{E}\left[ \frac{1}{2N+1} \lvert X^{N}(e^{j\Omega}) \rvert^{2} \right]
\end{align}
$$