---
title: "In a graph, what is a cut, an edge crossing the cut, and a safe edge"
tags:
  - dsa
  - flashcards
  - clrs
  - sorting
type: reference
status: completed
created: 2026-09-25
updated: 2026-09-25
aliases:
  - "In a graph, what is a cut, an edge crossing the cut, and a safe edge"
---

# 🎴 In a graph, what is a cut, an edge crossing the cut, and a safe edge

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: In a graph, what is a cut, an edge crossing the cut, and a safe edge? #card

?
Given a connected undirected weighted graph $G = (V, E)$ and $c : E \to \mathbb{R}$:

- **Cut:** a partition of the vertices $V$ into two proper, non-empty disjoint subsets $(S, V \setminus S)$, where $S \subset V$ and $0 < |S| < |V|$.
- **Edge crossing the cut:** any edge $e = (u,v) \in E$ such that one endpoint lies in $S$ and the other in $V \setminus S$ (i.e., $u \in S$ and $v \in V \setminus S$).
- **Safe Edge:** an edge $e = (u,v)$ of **minimum cost** among all those crossing the cut $(S, V \setminus S)$.
  Graphical representation of the _cut_:

The illustration above shows four edges crossing the cut (the partition of the graph's vertex set $V$ into two non-empty disjoint subsets) connecting the two subsets.
Among these, the edge e=(u,v) highlighted in red represents a generic edge crossing the cut and becomes the safe edge only if its cost is strictly less than or equal to that of each of the other edges.
