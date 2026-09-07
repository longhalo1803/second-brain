---
title: "What is the comparative table of computational costs for Disjoint Set (Base Versio..."
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
  - "What is the comparative table of computational costs for Disjoint Set (Base Versio..."
---

# 🎴 What is the comparative table of computational costs for Disjoint Set (Base Versio...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Graph Algorithms MOC|📁 Graph Algorithms MOC]]

---

### Q: What is the comparative table of computational costs for Disjoint Set (Base Version vs. Rank Heuristic)? #card

?
Comparative table of the worst-case computational cost for the primitives of a Disjoint Set with $n$ elements:

OperationBase Version (Without Heuristics)Rank Heuristic (Union by Rank)`Make-set(X)`$O(n)$$O(n)$`Find-set(DS, x)`$O(n)$$O(\log n)$`Union(DS, x, y)`$O(n)$$O(\log n)$
Applying the Rank Heuristic drastically reduces the execution times of the dynamic operations `Find-set` and `Union` from linear time $O(n)$ to logarithmic time $O(\log n)$.
