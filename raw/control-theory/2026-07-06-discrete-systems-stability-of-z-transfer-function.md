---
source: KaedeSync/_Knowledge/Control Theory/Discrete Systems/Stability of z-Transfer Function.md
ingested: 2026-07-06
---

[[z-Transform]]

Consider a system $G(z)$ subject to a delta input $\delta_{k}=\{ 1,0,0,\dots \}$ which indicates the z-transform $\Delta(z)=1$. What is the output sequence?
$$
y=\mathcal Z^{-1}[Y(z)]=\mathcal Z^{-1}[G(z)\Delta(z)]=\mathcal Z^{-1}[G(z)]
$$
Therefore, [[Poles]] of delta response $G(z)$ define the response to a delta input.

As we have learned in $2^{nd}$ year control theory, the polynomial transfer function can be resolved into linear decomposition of partial fractions of some simple forms. Therefore, in resemblance to continuous control theory, **stability of a discrete [[Linear Time-Invariant (LTI)]] system is dependent on the positioning of poles (of system transfer function) with respect to the unit circle.**

A system can have multiple poles, each (or each pair) positioned as one of the following cases:

- Real poles
$$
G(z)=\frac{1}{1-\lambda z^{-1}}\overset{\mathcal Z^{-1}}\to y_{k}=\lambda^{k}
$$
Therefore, the pole is stable for $|\lambda|<1$

![[Pasted image 20241022103634.png]]

- Complex (conjugate) poles
$$
G(z)=\frac{1}{1-(\lambda e^{j\theta}) z^{-1}}+\frac{1}{1-(\lambda e^{-j\theta}) z^{-1}}\overset{\mathcal Z^{-1}}\to y_{k}=\lambda^{k}(e^{j\theta k}+e^{-j\theta k})=2\lambda^{k}\cos(\theta k)
$$
Therefore, the pole is stable for $|\lambda|<1$

![[Pasted image 20241022103657.png]]

- Repeated poles
$$
G(z)=\frac{1}{(1-pz^{-1})^{2}}=\frac{1}{1-pz^{-1}}+\frac{pz^{-1}}{(1-pz^{-1})^{2}}\text{ then }\overset{\mathcal Z^{-1}}\to p^{k}+kp^{k}
$$
Therefore, the pole is stable for $|p|<1$

**Damping and Oscillation**
- *distance* of poles from origin is a measure of *decay rate*. The further the pole is from origin, the slower it decays.
- complex poles just inside unit circle give lightly damped oscillation.
- oscillation is possible for **real** poles on **negative** axis.
