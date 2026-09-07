---
title: "What is a forest Prove the formula for the total number of edges in a forest with..."
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
  - "What is a forest Prove the formula for the total number of edges in a forest with..."
---

# 🎴 What is a forest Prove the formula for the total number of edges in a forest with...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: What is a forest? Prove the formula for the total number of edges in a forest with $n$ nodes and $k$ trees. #card

?
A **forest** is a set of disjoint trees (an acyclic undirected graph).

**Proof for the number of edges $m$:**
Suppose the forest consists of $k$ trees $T_1, T_2, \dots, T_k$, where each tree $T_i$ has $n_i$ nodes and therefore $n_i - 1$ edges.
The total number of edges $m$ is the sum of the edges of each tree:

$$

\begin{aligned} m &= \sum*{i=1}^{k} (n_i - 1) \\ &= \sum*{i=1}^{k} n*i - \sum*{i=1}^{k} 1 \\ &= n - k \end{aligned}

$$

where $n = \sum_{i=1}^{k} n_i$ is the total number of nodes in the forest.
