---
source: KaedeSync/_Knowledge/Communications/Digital and Analog Conversion/Frequency Warping.md
ingested: 2026-07-08
---

What is the relationship of **frequency response** when [[Bilinear (Tustin's) Transformation]] is used for mapping?

Consider analogue prototype filter $G_{c}(s)$ and ADC mapping $s=\psi(z)$.  The digital filter is $G_{c}(\psi(z))$, so the normalised frequency response is given by:
$$
G(e^{j\theta})=G_{c}(\psi(e^{j\theta}))
$$

If [[Bilinear (Tustin's) Transformation]] is applied:
$$
G(e^{j\theta})=G_{c}(\psi(e^{j\theta}))=G_{c}\left( \frac{{e^{j\theta}-1}}{e^{j\theta}+1} \right)=G_{c}\left( \frac{{e^{j\theta/2}-e^{-j\theta/2}}}{e^{j\theta/2}+e^{-j\theta/2}} \right)=G_{c}\left( j\tan \frac{\theta}{2} \right)
$$
known as *frequency warping* relations.
**The frequency response of the digital filter at $\theta$ is mapped into the frequency response of the analog filter at $\tan \frac{\theta}{2}$.**

Inverse relation:
$$
G_{c}(j\omega)=G(e^{2j\arctan \omega})
$$
**The frequency response of the analog filter at $\omega$ is mapped into the frequency response of the digital filter at $2 \tan^{-1}\omega$.**


![[Pasted image 20241108182142.png]]