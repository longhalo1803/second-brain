---
title: "Describe an algorithm for constructing a Minimum Spanning Tree for an undirected g..."
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
  - "Describe an algorithm for constructing a Minimum Spanning Tree for an undirected g..."
---

# 🎴 Describe an algorithm for constructing a Minimum Spanning Tree for an undirected g...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: ❓ Describe an algorithm for constructing a Minimum Spanning Tree for an undirected graph $G = (V, E)$ and explain why it is correct. #card

?
**Kruskal's Algorithm:**

- **Description:**
- Initialize an edge set $T = \emptyset$.
- Create a disjoint forest where each vertex $v \in V$ forms its own set (using a _Disjoint-Set_ / _Union-Find_ data structure with primitive `Make-Set(v)`).
- Sort all edges of $E$ in non-decreasing order according to their weight $w(e)$: $e_1, e_2, \dots, e_{|E|}$.
- For each edge $(u, v)$ in sorted order:
- If `Find-Set(u)` $\ne$ `Find-Set(v)` (i.e., $u$ and $v$ belong to different connected components and the edge creates no cycle):
- Add $(u, v)$ to $T$.
- Execute `Union(u, v)`.
- The algorithm terminates when $|T| = |V| - 1$ (or all edges have been inspected), returning the spanning tree $T$.
- **Correctness:**
  Correctness is based on the **Cut Property**:

> _Let $G=(V,E)$ be an undirected, weighted graph. Let $A \subseteq E$ be a subset of edges contained in some MST for $G$. Let $(S, V \setminus S)$ be any cut of the graph that respects $A$ (i.e., no edge in $A$ crosses the cut). If $(u, v)$ is a minimum-weight edge crossing the cut (a light edge), then $A \cup \{(u, v)\}$ is also a subset of some MST._
> **Application to Kruskal:**
> Initially, $A = \emptyset$ is trivially part of an MST. When Kruskal considers the light edge $e = (u, v)$ connecting two distinct connected components $C_1$ and $C_2$, consider the cut defined by $S = C_1$ and $V \setminus S = V \setminus C_1$.
> All edges previously chosen in $A$ have both endpoints either inside $C_1$ or outside $C_1$, so no edge of $A$ crosses the cut (the cut respects $A$).
> Since edges are examined in increasing order of weight and no edge of smaller weight connects $C_1$ to the rest of the graph (otherwise the components would have already been merged), edge $(u, v)$ is the minimum-weight edge crossing the cut.
> By the cut property, $(u, v)$ is a **safe edge** for $A$. By induction, the algorithm always maintains a subset of an MST and terminates with a minimum spanning tree containing $|V|-1$ edges.
