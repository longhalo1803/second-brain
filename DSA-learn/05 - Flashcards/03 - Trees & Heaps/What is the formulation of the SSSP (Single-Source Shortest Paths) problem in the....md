---
title: "What is the formulation of the SSSP (Single-Source Shortest Paths) problem in the..."
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
  - "What is the formulation of the SSSP (Single-Source Shortest Paths) problem in the..."
---

# 🎴 What is the formulation of the SSSP (Single-Source Shortest Paths) problem in the...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: What is the formulation of the SSSP (Single-Source Shortest Paths) problem in the presence of negative edge weights? Input and output? #card

?
**Input:**

- A graph $G = (V, E)$ (directed or undirected) ****without negative cycles****;
- An edge cost function $c: E \to \mathbb{R}$ (which **may take negative values**);
- A source node $s \in V$.
  **Output:**
  The **shortest path tree** rooted at $s$ (represented via the shortest distances $\textsf{dist}[]$ and predecessors $\textsf{prev}[]$ for all reachable nodes).
