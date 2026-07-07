---
source: KaedeSync/_Knowledge/Computer Vision/Camera/Orthographic Projection.md
ingested: 2026-07-06
---

Project the scene onto image plane using *parallel* rays.

Assuming $\mathbf{x}$ is the vector for image on the image plane, $\mathbf{k}$ the viewing direction perpendicular to the image plane,, and $\mathbf{X}$ the object vector, then:

![[Pasted image 20251102122239.png]]

$$
\mathbf{x}=\mathbf{X}-(\mathbf{X}\cdot \mathbf{k})\mathbf{k}=(\mathbf{k}\times \mathbf{X})\times \mathbf{k}
$$

[[Projection]]