---
title: "📘 Exercise 17.1"
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
  - "📘 Exercise 17.1"
---

# 🎴 📘 Exercise 17.1

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: 📘 Exercise 17.1

**Input:** Two min-heaps $H_1$ and $H_2$ of sizes $n_1$ and $n_2$ respectively, with $n_1 > n_2$.
**Output:** Print all keys contained in the intersection of $H_1$ and $H_2$.

- Provide an example with $n_1, n_2 > 10$ and non-empty intersection.
- Design an algorithm using high-level heap operations (e.g. `extract_min`, `min`, `is_empty`), describe it, and provide pseudocode.
- Argue correctness and analyze computational complexity. #card
  ?
  **Reasoning:**
  Repeatedly extracting the minimum from a min-heap yields elements in sorted ascending order. We can simultaneously extract minimums from both heaps using a two-pointer-like merge step to identify common keys.

**1. Example:**
Let $H_1$ contain $[1, 3, 5, 7, 9, 11, 13, 15, 17, 19, 21, 23]$ ($n_1 = 12$) and $H_2$ contain $[2, 5, 8, 11, 14, 17, 20, 23, 26, 29, 32]$ ($n_2 = 11$).
Common keys printed: $5, 11, 17, 23$.

**2. Algorithm Description:**
Extract the minimums $x$ from $H_1$ and $y$ from $H_2$. While neither heap is exhausted: if $x = y$, print $x$ and extract new elements from both. If $x y$, extract next from $H_2$.

**3. Pseudocode:**

```text
Algorithm HeapIntersection(H_1, H_2):
    if is_empty(H_1) is_empty(H_2) then return
    x ≤ftarrow extract_min(H_1); \; y ≤ftarrow extract_min(H_2)
    while true do
        if x = y then
            print x
            if is_empty(H_1) is_empty(H_2) then return
            x ≤ftarrow extract_min(H_1); \; y ≤ftarrow extract_min(H_2)
        else if x < y then
            if is_empty(H_1) then return
            x ≤ftarrow extract_min(H_1)
        else
            if is_empty(H_2) then return
            y ≤ftarrow extract_min(H_2)
```

**Complexity:**
Each extraction takes $O(\log n)$. At most $n_1 + n_2$ extractions occur. Total time: $O((n_1 + n_2) \log n_1)$. Space: $O(1)$ auxiliary space.
