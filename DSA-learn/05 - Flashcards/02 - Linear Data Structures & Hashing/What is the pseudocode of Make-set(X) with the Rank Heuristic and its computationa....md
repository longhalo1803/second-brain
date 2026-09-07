---
title: "What is the pseudocode of Make-set(X) with the Rank Heuristic and its computationa..."
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
  - "What is the pseudocode of Make-set(X) with the Rank Heuristic and its computationa..."
---

# 🎴 What is the pseudocode of Make-set(X) with the Rank Heuristic and its computationa...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Linear Data Structures & Hashing MOC|📁 Linear Data Structures & Hashing MOC]]

---

### Q: What is the pseudocode of `Make-set(X)` with the Rank Heuristic and its computational cost? #card

?
With the rank heuristic, the `Make-set` algorithm simultaneously initializes the parent array `DS.p` and the rank array `DS.rank`:

```text
Make-set(X)
    {#f74040}{DS.p} := new_array[1..n]
    {#00a2ff}{DS.rank} := new_array[1..n]
    for i := 1 to n do
        {#f74040}{DS.p[i]} := i
        {#00a2ff}{DS.rank[i]} := 0           // {#D9534F}{≤ftarrow the initial rank of a singleton is 0}
    return DS
```

**Computational cost**: $\Theta(n)$ (or $O(n)$), as it allocates and iterates through two arrays of length $n$.
