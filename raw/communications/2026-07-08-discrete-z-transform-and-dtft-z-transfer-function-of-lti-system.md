---
source: KaedeSync/_Knowledge/Communications/Discrete/z-Transform and DTFT/z-Transfer Function of LTI System.md
ingested: 2026-07-08
---

A [[Linear Time-Invariant (LTI)]] system described by linear difference equations in [[Canonical Form]]
$$
y_{k}+a_{1}y_{k-1}+\dots+a_{n}y_{k-n}=b_{0}x_{k}+\dots+b_{m}x_{k-m}
$$
and subject to zero conditions
$$y_{k}=x_{k}=0\text{ for }k<0$$
gives in the $z$ domain:
$$
Y(z)+a_{1}z^{-1}Y(z)+\dots+a_{n}z^{-n}Y(z)=b_{0}X(z)+\dots+b_{m}z^{-m}X(z)
$$
**which gives the [[Transfer Function]]:**
$$
G(z)=\frac{Y(z)}{X(z)}= \frac{b_{0}+b_{1}z^{-1}+\dots+b_{m}z^{-m}}{1+a_{1}z^{-1}+\dots+a_{n}z^{-n}}
$$

###### Schematic, feed-forward and feedback
Here is a diagram of the system described by such LTI z-transfer function:

![[Pasted image 20241022102335.png]]

We can notice that there exists both feed-forward and feedback blocks in this loop.
- *The left block:*
$$
u'_{k}=u_{k}(b_{0}+b_{1}z^{-1}+b_{2}z^{-2}+\dots+b_{m}z^{-m})
$$
*the system is feed-forward: a signal is added by the lag of itself.*
- *The right block:*
$$
u'_{k}-y_{k}(a_{1}z^{-1}+a_{2}z^{-2}+\dots+a_{n}z^{-n})=y_{k}
$$
*the system is feedback: the input is subtracted from a lag of output.*
- *Therefore, we say that numerator is FIR filter and denominator is IIR filter.*

