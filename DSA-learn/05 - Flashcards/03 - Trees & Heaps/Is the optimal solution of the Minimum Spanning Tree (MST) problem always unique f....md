---
title: "Is the optimal solution of the Minimum Spanning Tree (MST) problem always unique f..."
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
  - "Is the optimal solution of the Minimum Spanning Tree (MST) problem always unique f..."
---

# 🎴 Is the optimal solution of the Minimum Spanning Tree (MST) problem always unique f...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: Is the optimal solution of the Minimum Spanning Tree (MST) problem always unique for a given graph? #card

?
**No**, the optimal solution (MST) **is not necessarily unique**.

A graph may admit multiple different spanning trees that achieve the same minimum total cost.

📌 Note:

- If all edges of the graph have **distinct weights**, the MST is **unique**.
- If, on the other hand, edges with the **same weight** are present, there may exist multiple distinct MSTs with the same total cost.
  📝 Example of a _unique_ optimal solution:

📝 Example of a _non-unique_ optimal solution:
In a graph G with 4 nodes and 4 edges all of weight 1, any choice of 3 edges constitutes a minimum spanning tree with a cost equal to 3 (there exist 4 distinct MSTs).

--- START OF FILE Paste September 13, 2026 - 5:18PM ---

Further example of two different optimal solutions for the following graph with repeated weights:
