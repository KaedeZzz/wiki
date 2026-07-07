---
source: KaedeSync/_Knowledge/Communications/Discrete/Digital Filtering/Window Methods.md
ingested: 2026-07-08
---

The window method *quickly design filters to give a target response*.
It does not explicitly impose amplitude constraints on the designed filter, so it has to be used iteratively to produce designs that meet specifications.

Steps:
1. Select a suitable window function $w_{k}$ . 
2. Specify an ideal frequency response $H$. 
3. Compute the coefficients of the ideal filter $h_{k}$ . 
4. Multiply the ideal coefficients by the window function to give the filter coefficients and delay to make causal. 
5. Evaluate the frequency response of the resulting filter and iterate 1-5 if necessary.