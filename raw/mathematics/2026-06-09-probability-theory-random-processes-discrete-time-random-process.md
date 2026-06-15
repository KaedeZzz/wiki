---
source: "KaedeSync/_Knowledge/Mathematics/Probability Theory/Random Processes/Discrete-time Random Process.md"
ingested: 2026-06-09
---

[[Definition of Random Process]]

We define a discrete-time random process as an ensemble of functions
$$
\{ X_{n}(\omega) \},\quad n=-\infty,\dots,-1,0,1,\infty
$$
$\omega$ is a random variable having a probability density function $f(\omega)$.

Think of a generative model for the waveform in practice:
1. First draw a random value $\tilde\omega$ from the density.
2. The observed waveform for this value $\omega=\tilde{\omega}$ is given by
$$
X_{n}(\tilde{\omega}),\quad n=-\infty,\dots,-1,0,1,\infty
$$
3. The ensemble is built up by considering all possible values $\tilde{\omega}$ and their corresponding time waveforms.
4. $f(\omega)$ determines the relative frequency with which each waveform occur.