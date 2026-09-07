---
title: "Present the Disjoint-set data structure and the implementation of the Union primit..."
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
  - "Present the Disjoint-set data structure and the implementation of the Union primit..."
---

# 🎴 Present the Disjoint-set data structure and the implementation of the Union primit...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: ❓ Present the Disjoint-set data structure and the implementation of the Union primitive with the union-by-rank heuristic. Explain what problem the union-by-rank heuristic solves compared to an implementation that does not use this heuristic. #card

?

- **Disjoint-Set Data Structure (Union-Find):**
  Maintains a partition of a set of $n$ elements into disjoint sets. Each set is identified by a representative element. Supported operations are:
- `Make-Set(x)`: creates a new set containing only element $x$.
- `Find-Set(x)`: returns the representative of the set containing $x$.
- `Union(x, y)`: merges the two sets containing $x$ and $y$ into a single set. In the tree-based forest implementation, each element points to its parent, and the representative is the root of the tree (pointing to itself).
- **Implementation of Union with Union by Rank:**
  Each node $x$ is associated with an integer `rank[x]`, which represents an upper bound on the height of the subtree rooted at $x$. Upon executing `Make-Set(x)`, we set `rank[x] = 0`.
  The operation `Union(x, y)` operates on roots $r_x = \text{Find-Set}(x)$ and $r_y = \text{Find-Set}(y)$:
- If `rank[r_x] > rank[r_y]`: root $r_x$ becomes parent of $r_y$ (overall height does not increase).
- If `rank[r_x] < rank[r_y]`: root $r_y$ becomes parent of $r_x$.
- If `rank[r_x] == rank[r_y]`: arbitrarily choose one of the two (e.g., $r_x$) as parent of the other and increment its rank by 1 (`rank[r_x]++`).
- **Problem solved by the rank heuristic:**
  In a naive implementation (without heuristics), a sequence of arbitrary unions can form degenerate trees resembling linear linked lists of height $\mathcal{O}(n)$. Under such a scenario, the cost of a single `Find-Set` operation degrades to $\mathcal{O}(n)$.
  Union by rank ensures that a tree with rank $r$ contains at least $2^r$ nodes, strictly bounding the maximum height of any tree to $\mathcal{O}(\log n)$. Consequently, the worst-case cost for `Find-Set` and `Union` operations drops to $\mathcal{O}(\log n)$ (and drops to nearly amortized constant time $\mathcal{O}(\alpha(n))$ when combined with path compression).
