---
title: "Given the frequency array C = [1, 0, 1, 2, 0, 1, 0, 2, 2, 0, 1] for k=10 computed..."
tags:
  - dsa
  - flashcards
  - clrs
  - sorting
type: reference
status: completed
created: 2026-09-25
updated: 2026-09-25
aliases:
  - "Given the frequency array C = [1, 0, 1, 2, 0, 1, 0, 2, 2, 0, 1] for k=10 computed..."
---

# 🎴 Given the frequency array C = [1, 0, 1, 2, 0, 1, 0, 2, 2, 0, 1] for k=10 computed...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: Given the frequency array $C = [1, 0, 1, 2, 0, 1, 0, 2, 2, 0, 1]$ for $k=10$ computed on array $A = \langle 5, 8, 3, 0, 8, 10, 7, 7, 3, 2 \rangle$, how is the array of **prefix sums** transformed in stable Counting Sort? #card

?
Applying the instruction $C[i] := C[i] + C[i-1]$ for $i$ from 1 to 10, the array is transformed as follows:

At the end:
Index $i$012345678910Frequencies10120102201Prefix sums $C[i]$112445579910
📌 Note: the final value of the last cell $C[k]$ always corresponds to $n$ (in this case $10$), confirming that there are 10 total elements $\le 10$.
