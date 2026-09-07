---
title: "How is the DP table structured for knapsack without repetition and in what order a..."
tags:
  - dsa
  - flashcards
  - clrs
  - data-structures
type: reference
status: completed
created: 2026-09-25
updated: 2026-09-25
aliases:
  - "How is the DP table structured for knapsack without repetition and in what order a..."
---

# 🎴 How is the DP table structured for knapsack without repetition and in what order a...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Linear Data Structures & Hashing MOC|📁 Linear Data Structures & Hashing MOC]]

---

### Q: How is the DP table structured for knapsack without repetition and in what order are the cells filled? #card

?
A matrix of size $(n+1) \times (W+1)$ is used, where the rows indicate the item indices $i = 0, 1, \dots, n$ and the columns represent the current capacities $w = 0, 1, \dots, W$.

To compute **$K(i, w)$** (to fill cell $(i,w)$) the values used are located:
• In the previous row ($i-1$) at column $w$.
• In the previous row ($i-1$) at the preceding column $w - w_i$.

The matrix is filled **row by row** (from top to bottom, for $i=1 \dots n$) and, within each row, **from left to right** (for $w=0 \dots W$).

i\w01.........W012.........n-1n
(Se si usa la convenzione $K(w,j)$, righe e colonne sono invertite:)

      w\j
      0
      1
      ...
      ...
      ...
      n




      0








      1








      2








      ...








      ...








      ...








      W-1








      W
