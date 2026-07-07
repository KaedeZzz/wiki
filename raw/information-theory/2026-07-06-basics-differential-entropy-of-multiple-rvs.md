---
source: KaedeSync/_Knowledge/Information Theory/Basics/Differential Entropy of Multiple RVs.md
ingested: 2026-07-06
---

Joint [[Differential Entropy]]:
$$
h(X,Y)=\int f_{XY}(u,v)\log \frac{1}{f_{XY}(u,v)}dudv
$$
Conditional differential entropy:
$$
h(X|Y)=\int f_{XY}(u,v)\log \frac{1}{f_{X|Y}(u,v)}dudv
$$
[[Chain Rule of Joint Entropy]] and [[Mutual Information]] follows discrete case.
