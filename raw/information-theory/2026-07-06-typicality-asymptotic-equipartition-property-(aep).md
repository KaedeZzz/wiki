---
source: KaedeSync/_Knowledge/Information Theory/Typicality/Asymptotic Equipartition Property (AEP).md
ingested: 2026-07-06
---

If $X_{1},X_{2},\dots$ are i.i.d. $\sim P_{X}$, then for any $\epsilon>0$
$$
\lim_{ n \to \infty } Pr\left(\left\lvert  - \frac{1}{n}\log P_{X}(X_{1},X_{2},\dots,X_{n})-H(X)  \right\rvert<\epsilon \right)=1
$$

Proof:
Let $Y_{i}=-\log P_{X}(X_{i})\text{ for }i=1,\dots,n$
[[Weak Law of Large Numbers]] states that for any $\epsilon>0$:
$$
\lim_{ n \to \infty }Pr\left(\left\lvert  \frac{1}{n}\sum_{i}Y_{i}-\mathbb{E}\{Y\}  \right\rvert<\epsilon \right)=1
$$
And we can note that $\sum_{i}Y_{i}=-\log P_{X}(X_{1},\dots,X_{n})$ and $\mathbb{E}\{\log P_{X}(X)\}=H(X)$
