---
source: "KaedeSync/_Knowledge/Mathematics/Differential Equations/Wave Equation/Harmonic Solution of Wave Equation.md"
ingested: 2026-06-09
---

Use 'separation of variable' principle:
$$
y(x,t)=U(x)T(t)
$$
Look for harmonic solutions, i.e. *sinusoidal in time*:
$$
y(x,t)=U(x)e^{i\omega t}
$$
Substitute into 1D wave equation, we get:
$$
U''+\frac{\omega ^{2}}{c^{2}}U=0
$$
The standard general solution is:
$$
U(x)=Ae^{-ikx}+Be^{ikx}
$$
In this case, $k=\frac{\omega}{c}$ is known as the ***wave number***. $\lambda=2\pi / k$ is the wavelength. This relation between wave number, wave speed, and angular velocity is known as the [[Dispersion]].

The overall solution is then:
$$
y(x,t)=Ae^{-ik(x- \frac\omega kt)}+Be^{-ik(x+ \frac\omega kt)}
$$
in which we find an important theorem:

![[Harmonic Free Motion Theorem]]

[[Wave Equation]]