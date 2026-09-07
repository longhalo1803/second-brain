---
title: "How many total nodes does a full and perfectly balanced binary tree of height h ha..."
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
  - "How many total nodes does a full and perfectly balanced binary tree of height h ha..."
---

# 🎴 How many total nodes does a full and perfectly balanced binary tree of height h ha...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: How many total nodes does a _full and perfectly balanced_ binary tree of height $h$ have? Prove it and derive the corollary regarding the height. #card

?
**Proposition:** a full and perfectly balanced binary tree of height $h \ge 0$ has exactly $n = \boxed{2^{h+1} - 1}$ nodes.

**Proof (for the number of nodes):**
For each level $i = 0, 1, \dots, h$, the number of nodes at level $i$ is equal to the number of leaves of a full and perfectly balanced binary tree of height $i$, which is $2^i$. Summing them over all levels:

$$

n = \sum\_{i=0}^{h} 2^i = \frac{2^{h+1}-1}{2-1} = 2^{h+1} - 1

$$

**Corollary (Height as a function of **$n$**):**
Solving for the height $h$ as a function of the total number of nodes $n$:

$$

\begin{aligned}n + 1 &= 2^{h+1} \\ \log_2(n+1) &= h + 1 \\ h &= \log_2(n+1) - 1 \in \Theta(\log n)\end{aligned}

$$

📌 Note: this proves that a full and perfectly balanced binary tree has a **logarithmic height with respect to the number of its nodes**.
