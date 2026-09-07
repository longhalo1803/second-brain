---
title: "What is the All-Pairs Shortest Paths (APSP) problem and what are its inputs and ou..."
tags:
  - dsa
  - flashcards
  - clrs
  - graphs
type: reference
status: completed
created: 2026-09-25
updated: 2026-09-25
aliases:
  - "What is the All-Pairs Shortest Paths (APSP) problem and what are its inputs and ou..."
---

# 🎴 What is the All-Pairs Shortest Paths (APSP) problem and what are its inputs and ou...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Graph Algorithms MOC|📁 Graph Algorithms MOC]]

---

### Q: What is the All-Pairs Shortest Paths (APSP) problem and what are its inputs and outputs? #card

?
The **All-Pairs Shortest Paths (APSP)** problem requires computing the length and sequence of the shortest paths between every possible pair of vertices in a weighted, directed graph.

**Input:**

- A directed graph $G = (V, E)$ with $V = \{1, 2, \dots, n\}$.
- An edge weight function $c: E \to \mathbb{R}$ that _does not produce negative-weight cycles_.**Output:**

- The shortest paths (and their lengths) between every pair of nodes $i, j \in V$.
  📌 Note: the absence of negative cycles is a necessary condition to ensure that the shortest paths are well-defined (in the presence of negative cycles, the shortest distance between nodes that can reach such a cycle would approach $-\infty$).
