---
title: "How does the search function search(L, i) work on a linked list and what is its co..."
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
  - "How does the search function search(L, i) work on a linked list and what is its co..."
---

# 🎴 How does the search function search(L, i) work on a linked list and what is its co...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Linear Data Structures & Hashing MOC|📁 Linear Data Structures & Hashing MOC]]

---

### Q: How does the search function `search(L, i)` work on a linked list and what is its computational cost? #card

?
The function `search(L, i)` traverses the list `L` starting from the head to find the pointer to the node at position `i` (0-indexed).
If position `i` exceeds the length of the list, it returns `NIL`.

**Pseudocode:**

```text
search(L, i)
    p := L
    j := 0
    while (j < i AND p ≠q NIL) do
        p := p.next
        j := j + 1
    return p
```

**Computational cost:** $\Theta(i)$ (worst case $\Theta(n)$, where $n$ is the length of the list).
