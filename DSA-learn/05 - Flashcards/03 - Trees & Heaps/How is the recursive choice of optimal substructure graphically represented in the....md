---
title: "How is the recursive choice of optimal substructure graphically represented in the..."
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
  - "How is the recursive choice of optimal substructure graphically represented in the..."
---

# 🎴 How is the recursive choice of optimal substructure graphically represented in the...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: How is the recursive choice of _optimal substructure_ graphically represented in the Floyd-Warshall algorithm for computing $\textsf{dist}(i, j, k)$? #card

?
The recursive choice evaluates whether the shortest path from $i$ to $j$ passes through intermediate node $k$ or not:

$\textsf{dist}(i, j, k) = \min \big( \textsf{dist}(i, j, k-1),\, \textsf{dist}(i, k, k-1) + \textsf{dist}(k, j, k-1) \big)$

**1. Option A (dashed line):** Path that _does not pass_ through $k$, with cost $\textsf{dist}(i, j, k-1)$.

**2. Option B (solid line):** Path that _passes_ through $k$, composed of the subpaths from $i$ to $k$ and from $k$ to $j$, with cost $\textsf{dist}(i, k, k-1) + \textsf{dist}(k, j, k-1)$.
