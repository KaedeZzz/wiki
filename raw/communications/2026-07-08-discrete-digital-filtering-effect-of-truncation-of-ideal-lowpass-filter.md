---
source: KaedeSync/_Knowledge/Communications/Discrete/Digital Filtering/Effect of Truncation of Ideal Lowpass Filter.md
ingested: 2026-07-08
---

Truncated delta response:
$$
g_{k}=\tilde{h}_{k}=h_{k-\frac{N}{2}}\text{ where }0\leq k\leq N
$$
we can view the truncation as multiplication by a rectangular window:
$$
g_{k}=\tilde{h}_{k}w_{k}\quad \text{ where }\quad w_{k}=
\begin{cases}
1\quad 0\leq k\leq N \\
0\quad \text{otherwise.}
\end{cases}
$$
From the [[Reverse Convolution Property of DTFT]], we can then derive the DTFT of $\{ g_{k} \}$ by convolving DTFT of $\{ \tilde h_{k} \}$ and $\{ w_{k} \}$.

The [[Discrete-time Fourier Transform (DTFT)]] of rectangular window:
$$
\begin{align}
W(\theta)&=\sum_{k=-\infty}^{\infty}w_{k}e^{-j\theta k}=\sum_{k=0}^{N}e^{j\theta k} \\
&= \frac{{1-e^{j\theta(N+1)}}}{1-e^{j\theta}} \\
&= e^{j\theta \frac{N}{2}} \frac{{\sin\left( \frac{\theta(N+1)}{2} \right)}}{\sin\left( \frac{\theta}{2} \right)}
\end{align}
$$
if $N$ is reasonably large (truncation keeps many samples), then, **within scope of period of** $\sin\left( \frac{\theta(N+1)}{2} \right)$, the denominator $\sin\left( \frac{\theta}{2} \right)$ will be tiny; thus, we can approximate it with $\frac{\theta}{2}$, and the magnitude of the term evaluates to
$$
|W(\theta)|\approx \frac{{\sin\left( \frac{\theta(N+1)}{2} \right)}}{\theta /2}=(N+1)\ \text{sinc}\ \frac{\theta(N+1)}{2}
$$
which is approximately a $\text{sinc}$ function -- exactly what we wanted.

What about further timesteps?

![[Pasted image 20250103024318.png]]
Note that:
- the *transition band* reduces as $N\to \infty$.
- ripples of $G$ are related to the area under side lobes, which remain constant as $N$ increases. 
How to improve that? Use different [[Filtering Windows]]

