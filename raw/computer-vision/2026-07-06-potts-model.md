---
source: KaedeSync/_Knowledge/Computer Vision/Potts Model.md
ingested: 2026-07-06
---

Motivated by image segmentation.

A [[Markov Network]] is constructed, where each pixel is a node, and each pair of neighbouring pixels are connected with an edge. 

If neighbouring pixels prefer the same label, the segmentation becomes smooth. So, the distribution:
$$
p(x_{1},\dots,x_{n})=\frac{1}{Z}\prod \phi_{ij}(x_{i},x_{j})
$$
and pairwise potential that rewards neighbouring labels being equal:
$$
\log \phi_{ij}(x_{i},x_{j})=
\begin{cases}
\beta>0, & x_{i}=x_{j} \\
0, & \text{otherwise.}
\end{cases}
$$

[[Computer Vision]]