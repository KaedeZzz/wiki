---
source: KaedeSync/_Knowledge/Communications/Digital and Analog Conversion/Step Invariance.md
ingested: 2026-07-08
---

$$
G_{c}(s)\overset{\text{step}}\to \frac{G_{c}(s)}{s}\overset{\mathcal L^{-1}}\to y(t)\overset{\text{sample}}\to y(kT)\overset{\mathcal Z}\to Y(z)\overset{\frac{1}{\text{step}}}\to \frac{{z-1}}{z}Y(z)=G(z)
$$
therefore:
$$
G(z)=\frac{{z-1}}{z}\mathcal Z\left( \mathcal L^{-1}\left( \frac{G_{c}(s)}{s} \right)_{t=kT} \right)
$$
