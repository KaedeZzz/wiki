---
source: KaedeSync/_Knowledge/Information Theory/Coding/Channel Coding/LDPC/Message Passing for Decoding Binary Erasure Channel.md
ingested: 2026-07-06
---

![[Message Passing]]

###### Steps

In the first step, $m_{vc}$ is the channel output corresponding to bit $v$: $(0,1,?)$, and all check nodes $c$ send $m_{cv}=?$ 

In each subsequent step:

![[Pasted image 20241202094456.png]]

In each step of the message passing decoder,
- $m_{vc}$: variable node $v$ tells check node $c$ its best guess of its own value (based on other incoming messages)
- $m_{cv}$: check node $c$ tells variable node $v$ what it thinks the value of $v$ should be (based on other incoming messages)

The complexity of message passing decoder
$$
\propto(\#\text{ edges in the graph})(\#\text{ iterations})
$$
Standard way of designing a good LDPC code based on message passing would be 
- choose a [[Degree Distribution]] that specifies distribution of weights on the nodes/edges on the graph
- fix code length $n$ and choose a $H$ based on selected degree distribution.

