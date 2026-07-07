---
source: KaedeSync/_Knowledge/Misc/Amdahl's Law.md
ingested: 2026-07-06
---

The performance enhancement possible with a given improvement is limited by the amount of the improved feature used. *Make the common case fast.*

$$
t_{\text{new}}=t_{\text{old}}\left[(1-\text{fraction}(\text{enhanced}))+ \frac{\text{fraction}(\text{enhanced})}{\text{speedup}(\text{enhanced})}\right]
$$