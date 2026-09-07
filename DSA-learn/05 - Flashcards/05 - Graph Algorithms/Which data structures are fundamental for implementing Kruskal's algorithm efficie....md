---
title: "Which data structures are fundamental for implementing Kruskal's algorithm efficie..."
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
  - "Which data structures are fundamental for implementing Kruskal's algorithm efficie..."
---

# 🎴 Which data structures are fundamental for implementing Kruskal's algorithm efficie...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Graph Algorithms MOC|📁 Graph Algorithms MOC]]

---

### Q: Which data structures are fundamental for implementing Kruskal's algorithm efficiently, and how do they prevent cycles from forming? #card

?
For an efficient implementation of Kruskal's algorithm, the following are used:

- **A list/set $T$** to store the selected edges that will form part of the MST.
- **A Disjoint Set (Union-Find) data structure $S$** defined over the vertex set $V$.
- Each connected component of the current forest is represented by a disjoint set.
- The operation `find-set(S, u)` returns the representative of the set to which node $u$ belongs.
- Checking whether adding edge $(u,v)$ creates a cycle is equivalent to verifying if:

$$
\text{find-set}(S, u) == \text{find-set}(S, v)
$$

- If they are **equal**, $u$ and $v$ are already connected (they belong to the same connected component) $\implies$ the edge creates a cycle and must be **discarded**.
- If they are **different**, the edge is **added** to $T$ and `union(S, u, v)` is executed to merge the two sets.

https://algorithms-visual.com/kruskal/ (click load to load pre-made graphs)
