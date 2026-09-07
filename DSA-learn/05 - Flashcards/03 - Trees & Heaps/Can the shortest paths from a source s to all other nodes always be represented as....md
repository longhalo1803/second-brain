---
title: "Can the shortest paths from a source s to all other nodes always be represented as..."
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
  - "Can the shortest paths from a source s to all other nodes always be represented as..."
---

# 🎴 Can the shortest paths from a source s to all other nodes always be represented as...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: Can the shortest paths from a source $s$ to all other nodes always be represented as a tree? #card

?
Yes. There always exists a tree structure that connects $s$ to all reachable nodes while preserving shortest path distances.
⚠️ However, the union of two arbitrary shortest paths is not necessarily a tree.

There are two paths to the orange (and light blue) node.
📌 Note:
The construction mechanism ensures that, when comparing two possible paths to a node (e.g., $L_1$ and $L_2$), if one were shorter than the other, the longer one would be excluded from the tree structure, preserving only the shortest path. If one of the two were shorter than the other (e.g., $L_1 < L_2$), the algorithm would immediately discard the longer route ($L_2$).
