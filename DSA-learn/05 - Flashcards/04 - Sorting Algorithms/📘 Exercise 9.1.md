---
title: "📘 Exercise 9.1"
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
  - "📘 Exercise 9.1"
---

# 🎴 📘 Exercise 9.1

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: 📘 Exercise 9.1

**Input:** A connected undirected graph $G = (V, E)$ with $V = \{1, \dots, n\}$, a positive edge-cost function $c : E \to \mathbb{R}^+$, and a subset $E' \subseteq E$ of disjoint edges (no two edges in $E'$ share an endpoint).
**Output:** A spanning tree of $G$ that includes all edges in $E'$ and minimizes the sum of edge costs not in $E'$.

Specify the data structure used to represent the spanning tree, describe the algorithm in words, provide pseudocode, and analyze its computational complexity. #card
?
**Reasoning:**
Since the edges in $E'$ are vertex-disjoint, they cannot form a cycle. We can adapt Kruskal's algorithm by pre-including all edges of $E'$ into the spanning forest, and then greedily adding the cheapest remaining edges from $E \setminus E'$ that connect distinct components.

**Data Structure:**
The spanning tree is represented as a set (or list) of edges $T_{edges}$. A Disjoint-Set (Union-Find) structure tracks connected components.

**Pseudocode:**

```text
Algorithm ConstrainedMST(G, c, E'):
    T_{edges} ≤ftarrow
    for each v ∈ V do MakeSet(v)
    for each (u, v) ∈ E' do
        Union(u, v)
        T_{edges} ≤ftarrow T_{edges} {(u, v)}
    E_{rem} ≤ftarrow sort E E' in non-decreasing order of cost c
    for each (u, v) ∈ E_{rem} do
        if FindSet(u) ≠ FindSet(v) then
            Union(u, v)
            T_{edges} ≤ftarrow T_{edges} {(u, v)}
    return T_{edges}
```

**Complexity:**

- Time Complexity: Sorting $|E|$ edges takes $O(|E| \log |E|)$. Disjoint-set operations take $O(|E| \alpha(|V|))$. Total time is $O(|E| \log |V|)$.
- Space Complexity: $O(|V| + |E|)$ for the edge list and disjoint-set arrays.
