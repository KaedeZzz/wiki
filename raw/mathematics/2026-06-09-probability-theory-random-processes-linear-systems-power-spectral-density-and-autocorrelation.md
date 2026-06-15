---
source: "KaedeSync/_Knowledge/Mathematics/Probability Theory/Random Processes/Linear Systems/Power Spectral Density and Autocorrelation.md"
ingested: 2026-06-09
---


$$
\begin{align}
\frac{1}{N}\mathbb{E}\{|X(\theta)|^{2}\} & =\frac{1}{N}\mathbb{E}\{X(\theta)X^{*}(\theta)\} \\
 & =\frac{1}{N}\mathbb{E}\left\{ \left( \sum_{k}X_{k}e^{-jk\theta} \right)\left( \sum_{k}X_{k}e^{jk\theta} \right) \right\} \\
 & =\frac{1}{N}\sum_{k}\sum_{m}\mathbb{E}\{X_{k}X_{m}\}e^{-jk\theta}e^{jm\theta} \\
( m=k-n)& =\frac{1}{N}\sum_{k}\sum_{n}\mathbb{E}\{X_{k}X_{k-n}\}e^{-jk\theta}e^{j(k-n)\theta} \\
 & =\frac{1}{N}\sum_{k}\sum_{n}r_{XX}(n)e^{-jn\theta} \\
 & =\sum_{n}r_{XX}(n)e^{-jn\theta}
\end{align}
$$

The (discrete) [[Power Spectral Density Function]] is the [[Discrete-time Fourier Transform (DTFT)]] of the [[Autocorrelation]] function.

Hence, from the [[Reverse Convolution Property of DTFT]], the relation for filtering [[White Noise]]through a linear system
$$
\Phi_{YY}(\theta)=|H(\theta)|^{2}
$$

becomes in the time domain
$$
r_{YY}(n)=\{ h_{k} \}*\{ h_{-k} \}
$$
