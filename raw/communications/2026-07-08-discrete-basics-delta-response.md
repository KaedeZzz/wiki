---
source: KaedeSync/_Knowledge/Communications/Discrete/Basics/Delta Response.md
ingested: 2026-07-08
---

[[Discrete-time Signals]]

The Kronecker delta signal is defined as:
$$
\{  \delta_{k} \}_{k>0}=\{ 1,0,0,0\dots \}
$$

*Relate to continuous control theory where value of input signals at some time instant can be written as convolution of signal and delta function,* every input signal to $\{ u_{k} \}$ to an [[Linear Time-Invariant (LTI)]] system can be written as a [[Discrete Convolution]]:
$$
u_{k}=\sum_{n=-\infty}^{\infty}\delta_{n}u_{k-n}
$$
*Why？ $\delta_{n}=0$ only if $n=0$.*

Denote $y=\mathcal L[u]$ as the solution of difference equation for input signal $u$.
Since the system is [[Linear Time-Invariant (LTI)]], we can use superposition principle to find that:
$$
\begin{align}
y_{k}&=\mathcal L[u_{k}] \\
&= \mathcal L\left[ \sum_{n=-\infty}^{\infty}\delta_{n}u_{k-n} \right] \\
&=\sum_{n=-\infty}^{\infty}\mathcal L[\delta_{n}]u_{k-n} \\
&=\sum_{n=-\infty}^{\infty}g_{n}u_{k-n}
\end{align}

$$
 where $\{ g_{k} \}$ is known as the ***delta response*** of the LTIS.
 
*Knowing $\{ g_{k} \}$ describes the system, just as knowing the impulse response describes a continuous system.*