---
source: KaedeSync/_Knowledge/Information Theory/Typicality/Joint AEP.md
ingested: 2026-07-06
---

For any $\epsilon>0$:
1. $\text{Pr}((X^{n},Y^{n})\in A_{\epsilon,n})\to 1$
2. $|A_{\epsilon,n}|<2^{n(H(X,Y)+\epsilon)}$
3. If $\tilde{X}^{n},\tilde{Y}^{n} \in A_{\epsilon,n}$ are a pair of sequences drawn i.i.d. according to $P_{X}P_{Y}$ （two marginals of $P_{XY}$), then
$$
Pr((\tilde{ X}^{n},\tilde{Y}^{n})\in A_{\epsilon,n})\leq 2^{-n(I(X;Y)-3\epsilon)}
$$
Proof:
$$
\begin{align}
Pr((\tilde{ X}^{n},\tilde{Y}^{n})\in A_{\epsilon,n})&=\sum_{(x^{n},y^{n})\in A_{\epsilon,n}}P_{X}(x^{n})P_{Y}(y^{n}) \\
&\leq\underbrace{2^{n(H(X,Y)+\epsilon)}}_{\text{from summation}}\cdot\underbrace{2^{-n(H(X)+\epsilon)}}_{P_{X}}\cdot\underbrace{2^{-n(H(Y)+\epsilon)}}_{P_{Y}} \\
 & = 2^{-n(I(X;Y)-3\epsilon)}
\end{align}
$$

[[Jointly Typical]], [[Asymptotic Equipartition Property (AEP)]]