---
title: "Exercise 1"
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
  - "Exercise 1"
---

# 🎴 Exercise 1

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Graph Algorithms MOC|📁 Graph Algorithms MOC]]

---

### Q: 📝 Exercise 1

Given a graph $G = (V, E)$ (directed or undirected) and two nodes $u, v \in V$, write a function $\textsf{EdgeExists}(u, v)$ that returns TRUE if an edge $(u, v) \in E$ exists, and FALSE otherwise.
Write two versions, one assuming the graph is represented using an adjacency matrix, and the other using adjacency lists, and for each version, calculate the computational cost of the function. #card
?
**1. Adjacency matrix:**
It suffices to check whether a one or a zero is stored in the matrix cell corresponding to nodes $u$ and $v$:

```text
EdgeExists(G, u, v)
    if G[u, v] = 1
        then return TRUE
        else return FALSE
```

The computational cost is that of accessing a cell in a matrix, which is constant: $\Theta(1)$.

**2. Adjacency lists:**
One must traverse the list pointed to by $\textsf{G}[u]$ and search for an element in the list storing $v$:

```text
EdgeExists(G, u, v)
    L := G[u]
    while L ≠q NIL do
        if L.val = v then return TRUE
        L := L.next
    return FALSE
```

The computational cost is that of traversing the list of neighbors. In general, we cannot rule out that node $u$ has all other nodes as neighbors (worst case, in which the list to traverse is as long as possible), so the computational cost is $O(n)$.
