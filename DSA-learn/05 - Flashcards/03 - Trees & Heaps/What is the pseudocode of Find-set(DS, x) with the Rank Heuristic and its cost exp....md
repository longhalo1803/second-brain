---
title: "What is the pseudocode of Find-set(DS, x) with the Rank Heuristic and its cost exp..."
tags:
  - dsa
  - flashcards
  - clrs
  - trees-heaps
type: reference
status: completed
created: 2026-09-25
updated: 2026-09-25
aliases:
  - "What is the pseudocode of Find-set(DS, x) with the Rank Heuristic and its cost exp..."
---

# 🎴 What is the pseudocode of Find-set(DS, x) with the Rank Heuristic and its cost exp...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: What is the pseudocode of `Find-set(DS, x)` with the Rank Heuristic and its cost expressed as a function of rank? #card

?
The pseudocode of `Find-set` ascends the tree up to the root by accessing the array `DS.p`:

```text
Find-set(DS, x)
    if {#f74040}{DS.p[x]} = x then
        return x
    else
        return Find-set(DS, {#f74040}{DS.p[x]})
```

**Computational cost**: $O(\textsf{rank}[\text{representative of } x])$.
Since the rank of the set representative upper-bounds the height of the tree, the traversal takes time proportional to the rank of the root.
