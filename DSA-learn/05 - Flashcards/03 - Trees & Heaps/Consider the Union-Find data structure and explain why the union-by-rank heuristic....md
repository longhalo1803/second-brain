---
title: "Consider the Union-Find data structure and explain why the union-by-rank heuristic..."
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
  - "Consider the Union-Find data structure and explain why the union-by-rank heuristic..."
---

# 🎴 Consider the Union-Find data structure and explain why the union-by-rank heuristic...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: ❓ Consider the Union-Find data structure and explain why the union-by-rank heuristic was introduced. State what result is achieved through its introduction and prove its validity in the case of equal ranks. #card

?

- **Motivation for the Union-by-Rank Heuristic:**
  In a tree-based Union-Find data structure, naive unions can produce degenerate linear chains (trees of linear height $\mathcal{O}(n)$). In that case, subsequent search operations (`Find-Set`) would take $\mathcal{O}(n)$ time. The union-by-rank heuristic (_Union by Rank_) was introduced to balance the structure and keep tree heights logarithmically bounded relative to the number of nodes.
- **Result Achieved:**
  The union-by-rank heuristic ensures that a tree with a root of rank $r$ contains **at least $2^r$ nodes**. As a direct consequence:

$$

2^r \le n \implies r \le \lfloor \log_2 n \rfloor

$$

Because the height of the tree never exceeds its rank, the maximum height is strictly bounded by $\mathcal{O}(\log n)$, reducing the worst-case cost of `Find-Set` and `Union` operations to at most $\mathcal{O}(\log n)$.

- **Proof in the case of equal ranks:**
  We proceed by induction on rank $r$:
- **Base Case ($r=0$):** A tree of rank $0$ contains at least $2^0 = 1$ node (the root newly created by `Make-Set`). The property holds.
- **Inductive Hypothesis:** Assume that any tree with a root of rank $r-1$ contains at least $2^{r-1}$ nodes.
- **Inductive Step (equal rank):** The only operation that can increase the rank of a root to $r$ is merging (`Union`) two trees whose roots have the **same rank** equal to $r-1$.
  Let $T_1$ and $T_2$ be two disjoint trees both of rank $r-1$. By the inductive hypothesis, $T_1$ has at least $2^{r-1}$ nodes and $T_2$ has at least $2^{r-1}$ nodes.
  When making the root of $T_2$ a child of the root of $T_1$, the rank of the root of $T_1$ increases to $(r-1) + 1 = r$.
  The total number of nodes in the new tree $T$ is:

$$

|T| = |T_1| + |T_2| \ge 2^{r-1} + 2^{r-1} = 2 \cdot 2^{r-1} = 2^r

$$

The property is thus proven: to increase rank to $r$, the number of nodes must double, guaranteeing it contains at least $2^r$ elements.
