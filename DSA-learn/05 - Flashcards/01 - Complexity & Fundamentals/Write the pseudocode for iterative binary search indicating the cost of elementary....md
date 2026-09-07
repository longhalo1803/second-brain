---
title: "Write the pseudocode for iterative binary search indicating the cost of elementary..."
tags:
  - dsa
  - flashcards
  - clrs
  - complexity
type: reference
status: completed
created: 2026-09-25
updated: 2026-09-25
aliases:
  - "Write the pseudocode for iterative binary search indicating the cost of elementary..."
---

# 🎴 Write the pseudocode for iterative binary search indicating the cost of elementary...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Complexity & Fundamentals MOC|📁 Complexity & Fundamentals MOC]]

---

### Q: 🟢 Write the pseudocode for **iterative binary search** indicating the cost of elementary operations (excluding the loop). #card

?

```text
BinarySearch(L, n, key)
    i := 0                               // {#D9534F}{{O}(1)}
    j := n - 1                           // {#D9534F}{{O}(1)}
    while i ≤ j do
        k := floor((i + j) / 2)              // {#D9534F}{{O}(1)}
        if key = L[k] then
            return k
        if key https://coddy.tech/visualize/searching/binary-search
```
