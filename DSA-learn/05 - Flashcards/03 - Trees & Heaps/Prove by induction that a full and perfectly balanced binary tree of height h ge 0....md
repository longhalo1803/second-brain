---
title: "Prove by induction that a full and perfectly balanced binary tree of height h ge 0..."
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
  - "Prove by induction that a full and perfectly balanced binary tree of height h ge 0..."
---

# 🎴 Prove by induction that a full and perfectly balanced binary tree of height h ge 0...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: Prove by induction that a full and perfectly balanced binary tree of height $h \ge 0$ has $2^h$ leaves. #card

?
**Proposition:** a full and perfectly balanced binary tree of height $h \ge 0$ has exactly $\boxed{2^h}$ leaves.

**Proof by induction (on the number of leaves):**

- **Base Case ($h = 0$):** A tree of height 0 has only one node (the root). The number of leaves is $1 = 2^0$.
- **Inductive Hypothesis:** Assume that a full and perfectly balanced binary tree of height $h - 1 \ge 0$ has $2^{h-1}$ leaves.
- **Inductive Step:
  **We prove that the property holds for a tree of height $h$:

- The tree of height $h$ contains within it a tree of height $h - 1$, whose leaves constitute the nodes of the second-to-last level (level $h - 1$).
- By the inductive hypothesis, the nodes at level $h - 1$ are exactly $2^{h-1}$.
- Since the tree is full, every node of the second-to-last level has exactly two children at level $h$, which represent all the leaves of the final tree.
- The total number of leaves is therefore:

$$

2^{h-1} \cdot 2 = 2^h

$$

The proposition is thus proven for every $h \ge 0$.
