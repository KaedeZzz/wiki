---
source: "KaedeSync/_Knowledge/Mathematics/Probability Theory/Random Processes/Power Spectrum.md"
ingested: 2026-06-09
---

The power spectral density is the [[Fourier Transform]] of the [[Autocorrelation]] $R_{X}(k)$:
$$
S_{X}(e^{i\omega})=\sum_{k=-\infty}^{\infty}R_{X}(k)e^{-ik\omega}
$$
 Inversion:
 $$
R_{X}(k)=\frac{1}{2\pi}\int_{-\pi}^{\pi}S_{X}(e^{i\omega})e^{ik\omega}d\omega
$$

For real [[Wide-Sense Stationary]] $\{ X_{t} \}$, the power spectrum is **even, real, and non-negative.**
