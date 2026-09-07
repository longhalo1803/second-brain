---
title: "Give the definition of a complete and perfectly balanced binary tree. In general,..."
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
  - "Give the definition of a complete and perfectly balanced binary tree. In general,..."
---

# 🎴 Give the definition of a complete and perfectly balanced binary tree. In general,...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: ❓ Give the definition of a complete and perfectly balanced binary tree. In general, (1) how many leaves does a complete and perfectly balanced binary tree of height $h$ have? (2) And how many nodes? Prove one of the two statements. #card

?

- **Definition:**
  A binary tree is called **complete and perfectly balanced** (or full and complete) if every internal node has exactly two children and all leaves are strictly at the same depth $h$ (where the height $h$ is the length in number of edges of the path from the root to a leaf).
- **General formulas:**
- (1) Number of leaves: $L(h) = 2^h$.
- (2) Total number of nodes: $N(h) = 2^{h+1} - 1$.
- **Proof for the number of nodes $N(h) = 2^{h+1} - 1$ (by induction on $h$):**
- **Base Case ($h=0$):** The tree has only the root. Thus $N(0) = 1$. Applying the formula: $2^{0+1} - 1 = 2 - 1 = 1$. The base case holds.
- **Inductive Hypothesis:** Assume the relation holds for a complete and perfectly balanced tree of height $h-1$, that is, $N(h-1) = 2^{(h-1)+1} - 1 = 2^h - 1$.
- **Inductive Step (height $h$):** A tree of height $h$ consists of the root plus two complete and balanced subtrees of height $h-1$. Thus:

$$

N(h) = 1 + N*{\text{left}}(h-1) + N*{\text{right}}(h-1) = 1 + (2^h - 1) + (2^h - 1) = 2 \cdot 2^h - 1 = 2^{h+1} - 1

$$

The claim is proven for all $h \ge 0$.
