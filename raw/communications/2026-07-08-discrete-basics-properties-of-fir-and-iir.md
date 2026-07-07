---
source: KaedeSync/_Knowledge/Communications/Discrete/Basics/Properties of FIR and IIR.md
ingested: 2026-07-08
---

#ESSENTIAL 
How would response from [[FIR and IIR]] differ, and how would we describe them?

Finite impulse response can be described by a **finite-degree polynomial** of $z^{-1}$. That is, $FIR=\sum_{i=1}^{n}a_{i}z^{-i}$. Therefore, it can be considered as a **summation** of many time-delay filters in parallel, each of which being a $n$-step time delay operator; thus, we say FIR is ***feedforward***.

Infinite impulse response, on the other hand, cannot be defined by a finite-degree polynomial, and must be a series of $z^{-1}$. *Generation of series necessarily indicates **division** with finite-degree polynomial*; for example, $\frac{1}{1-z^{-1}}=1+z^{-1}+z^{-2}+\dots$ Therefore, as transfer function being a series of $z^{-1}$, there is definitely finite-degree polynomial of $z^{-1}$ at the **denominator** of delta transfer function, which leads into from of $Y= \frac{K}{1+KB}X$ where $K$ is a feed-forward filter and $B$ is a feedback filter, forming a **feedback loop**. Thus, we say IIR is **feedback**.