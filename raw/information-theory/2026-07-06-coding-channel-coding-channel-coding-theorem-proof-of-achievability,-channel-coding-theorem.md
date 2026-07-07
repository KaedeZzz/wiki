---
source: KaedeSync/_Knowledge/Information Theory/Coding/Channel Coding/Channel Coding Theorem/Proof of Achievability, Channel Coding Theorem.md
ingested: 2026-07-06
---

[[Channel Coding Theorem]]

###### Codebook generation

(As a thought experiment) 
#SUPO Backbone of the proof: random of codeword and codebook, and average

pick every symbol of every codeword iid from capacity achieving distribution

We generate each of the $2^{nR}$ codewords **independently** according to the distribution
#SUPO : what does it actually mean?
$$
Pr(X^{n}(k)=(x_{1},\dots,x_{n}))=\prod_{i=1}^{n}P_{X}(x_{i}) \quad \text{for }k=1,2,\dots,2^{nR}
$$
*i.e. the probability of input message is from i.i.d. input [[Probability Mass Function]]s.*

Codebook: we can think of the codebook as a $2^{nR}\times n$ matrix:
$$
\mathcal B=
\begin{bmatrix}
X_{1}(1) & X_{2}(1) & \dots & X_{n}(1) \\
X_{1}(2) & X_{2}(2) & \dots & X_{n}(2) \\
\vdots & \vdots &  & \vdots \\
X_{1}(2^{nR}) & X_{2}(2^{nR}) & \dots & X_{n}(2^{nR})
\end{bmatrix}
$$
*the codebook is just a matrix where each row is a codeword.*

The probability that we generate a particular codebook $\{ x^{n}(1),\dots,x^{n}(2^{nR}) \}$ *is the product of probability of all individual codebooks, i.e.* 
$$
\prod_{w=1}^{2^{nR}}\prod_{i=1}^{n}P_{X}(x_{i}(w))
$$

To transmit message $W$, the encoder sends $X^{n}(W)$ over the channel, and the receiver receives a sequence $Y^{n}$ generated according to channel probability
$$
\prod_{i=1}^{n}P_{Y|X}(Y_{i}|X_{i}(W))
$$
and guess the message from $Y^{n}$. 

**How to Decode?**
- one way: max-likelihood decoding
- another way: joint typical decoding

![[Joint Typical Encoding]]

###### Analysing Probability of Error

The average probability of error for a given codebook $\mathcal B$ is:
$$
\frac{1}{2^{nR}}\sum_{w=1}^{2^{nR}}Pr(\hat{W}\neq w|\mathcal B,W=w)
$$
average error of probability over all codebooks (expectation):
$$
\bar{P_{e}}=\frac{1}{2^{nR}}\sum_{\mathcal B}\sum_{w=1}^{2^{nR}}Pr(\hat{W}\neq w|\mathcal B, W=w)Pr(\mathcal B)
$$

*Since we generate all codewords i.i.d. with respect to the input pmf, all messages in a codebook should have equal error probability.* #SUPO  
therefore, assume the first message is the transmitted one:
$$
\bar{ P_{e}}=\sum_{\mathcal B}Pr(\hat{ W}\neq 1|\mathcal B,W=1)Pr(\mathcal B)
$$
Assuming $W=1$ is transmitted, there are two sources of error:
1. $X^{n}(1)$ is not jointly typical with the output $Y^{n}$.
2. $X^{n}(k)$ is jointly typical with $Y^{n}$ for some $k\neq 1$.

**Let $E_{k}$ be the event that $X^{n}(k)$ and $Y^{n}$ are jointly typical.** Then:
$$
\begin{align}
\bar{P_{e}} & =P(E_{1}^{c}\cup E_{2}\cup\dots\cup E_{2^{nR}}) \\
 & \leq P(E_{1}^{c})+P(E_{2})+\dots+P(E_{2^{nR}})
\end{align}
$$
*note that cups denote "or".*

Firstly, $P(E_{1}^{c})$ is small:
- recall that $X^{n}(1)$ is i.i.d. $\sim P_{X}$.
- The channel generates $Y^{n}$ symbol by symbol according to $P_{Y|X}(Y_{i}|X_{i}(1))$. Therefore $(X^{n}(1),Y^{n})$ is generated i.i.d. $\sim P_{X}P_{Y|X}$.
- [[Joint AEP]] implies that $P(E_{1}^{c})<\epsilon$ for sufficiently large $n$.

Secondly, $P(E_{2})+\dots+P(E_{2^{nR}})$ is small: for $k\neq 1$,
- $X^{n}(k)$ was generated independently from $X^{n}(1)$, and $Y^{n}$ is obtained by passing $X^{n}(1)$ through the channel.
- Hence $X^{n}(k)$ and $Y^{n}$ are independent for $k\neq 1$.
- Furthermore, $X^{n}(k)$ is i.i.d. $\sim P_{X}$, and $Y^{n}$ is i.i.d. $\sim P_{Y}$.

From the [[Joint AEP]], the probability that $X^{n}(k)$ and $Y^{n}$ are jointly typical according to $P_{XY}$ is $\leq 2^{-n(I(X;Y)-3\epsilon)}$. The total probability is then $(2^{nR}-1)2^{-n(I(X;Y)-3\epsilon)}$

Putting two parts together:
$$
\begin{align}
\bar{P_{e}}
 & \leq P(E_{1}^{c})+P(E_{2})+\dots+P(E_{2^{nR}}) \\
 & \leq\epsilon +(2^{nR}-1)2^{-n(I(X;Y)-3\epsilon)} \\
 & \leq\epsilon +2^{nR}2^{-n(I(X;Y)-3\epsilon)} \\
 & \leq\epsilon +2^{n{(R-(I(X;Y)-3\epsilon))}}  \\
& \leq\epsilon+\epsilon=2\epsilon
\end{align}
$$
given that $R<I(X;Y)-3\epsilon$ and $n$ is sufficiently large.
#SUPO what is the mathematical basis of this? CHOICE! This is the cleverest point of CCT.

###### Final Steps

1. Choose $P_{X}$ to be one that maximises $I(X;Y)$.
2. As $\bar{P}_{e}\leq 2\epsilon$, there exists at least one codebook $\mathcal B^{*}$ with $P_{e}(\mathcal B^{*})<2\epsilon$.
3. Since the probability of error *averaged over all messages* are $\leq 2\epsilon$, the probability of error must be $\leq 4\epsilon$ for at least half of the messages.
4. Throw away the worst half of the codebook; the number of codewords in the improved version of $\mathcal B^{*}$ is $2^{nR-1}$. Its rate is
$$
\frac{\log(2^{nR-1})}{n}=R-\frac{1}{n}
$$
Since $R$ is any rate less than $C-3\epsilon$, we have shown that the existence of a code with rate
$$
C-4\epsilon-\frac{1}{n}
$$
whose *maximal probability* of error satisfies
$$
\max_{w}Pr(\hat{W}\neq w|W=w)\leq 4\epsilon
$$
Therefore, for any arbitrary $\epsilon$, for sufficiently large $n$, there exists code with rate $R<\mathcal C$ that has lower max probability of error $<\epsilon$.

**Proof**.
