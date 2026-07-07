---
source: KaedeSync/_Knowledge/Information Theory/Basics/Proof of Fano's Inequality.md
ingested: 2026-07-06
---

Define an error random variable
$$
E=\begin{cases}
1\quad \text{if}\quad \hat{X}\neq X  \\
0\quad \text{if}\quad \hat{X}=X
\end{cases}
$$
Use the chain rule to expand $H(E,X|\hat{X})$ in two different ways:
$$
\begin{align}
H(E,X|\hat{X}) & =H(X|\hat{X})+H(E|X,\hat{X}) \\
& =H(E|\hat{X})+H(X|\hat{X},E)
\end{align}
$$
claims:
1. $H(E|X,\hat{X})=0$ because $E$ is a function of $(X,\hat{X})$
2. From [[The Data Processing Inequality]], $H(E|\hat{X})\leq H(E)=H_{2}(P_{e})$.
3. $H(X|\hat{X},E)\leq P_{e}\log|\mathcal X|$ because
$$
\begin{align}
H(X|\hat{X},E) & =Pr(E=0)H(X|\hat{X},E=0)+Pr(E=1)H(X|\hat{X},E=1) \\
 & =(1-P_{e})0+Pr(E=1)H(X|\hat{X},E=1) \\
 & \leq P_{e}\log|\mathcal X|
\end{align}
$$

Therefore,
$$
H(X|\hat{X})=H(E|\hat{X})+H(X|\hat{X},E)\leq H_{2}(P_{e})+P_{e}\log|\mathcal X|\leq{1}+P_{e}\log|\mathcal X|
$$
one side of Fano's inequality is proved. The other side:
$$
I(X;Y)=H(X)-H(X|Y)\geq I(X;\hat{X})=H(X)-H(X|\hat{X})
$$
so
$$
H(X|\hat{X})\geq H(X|Y)
$$
