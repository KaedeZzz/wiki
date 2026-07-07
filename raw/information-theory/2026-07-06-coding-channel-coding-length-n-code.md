---
source: KaedeSync/_Knowledge/Information Theory/Coding/Channel Coding/length-n Code.md
ingested: 2026-07-06
---

[[Channel Coding]]

Definition of $(n,k)$ channel code:

We use the channel $n$ times to transmit $k$ information bits. 
- The rate $R$ of the code is $R=\frac{k}{n}$ bits/transmission. Then the total number of messages is $2^{k}=2^{nR}$.

An $(n,k)$ channel code of rate $R$ for the channel $(\mathcal{X},\mathcal Y,P_{Y|X} )$ consists of:
1. A set of messages $\{ 1,\dots,2^{k }=2^{nR}\}$
2. An encoding function $X^{n}: \{ 1,\dots,2^{nR} \}\to \mathcal X^{n}$ that assigns a codeword to each message. The set of codewords $\{ \mathcal X^{n}(1),\dots, \mathcal X^{n}(2^{nR})\}$ is known as the *codebook*. 
3. A decoding function $g: \mathcal Y^{n}\to \{ 1,\dots,2^{nR} \}$ which produces a guess of the transmitted message for each received vector.

