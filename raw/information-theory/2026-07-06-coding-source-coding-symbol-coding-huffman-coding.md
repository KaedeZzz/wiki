---
source: KaedeSync/_Knowledge/Information Theory/Coding/Source Coding/Symbol Coding/Huffman Coding.md
ingested: 2026-07-06
---

[[Source Coding]]
Huffman is a simple algorithm that gives **optimal** [[Prefix-free Code]] for a given set of probabilities.

The algorithm is as follows:
1. Take the two least probable symbols in the alphabet. These two symbols will be given the longest codewords, which will have equal length, and differ only in the last digit.
2. Combine these two symbols into a single symbol (with probability added).
3. Repeat.

It guarantees a prefix code because all symbol nodes are leaves.

