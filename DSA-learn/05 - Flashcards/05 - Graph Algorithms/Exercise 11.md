---
title: "Exercise 11"
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
  - "Exercise 11"
---

# 🎴 Exercise 11

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Graph Algorithms MOC|📁 Graph Algorithms MOC]]

---

### Q: 📝 Exercise 11

Given a directed graph $G = (V, E)$, the transpose graph $G^T = (V^T, E^T)$ is defined as a graph having the same nodes as $G$ but directed edges in the reverse direction relative to $G$. Formally, $V^T = V$ and if $(u, v) \in E$ then $(v, u) \in E^T$.
Write an algorithm that, given as input a graph $G$, returns a new graph that is the transpose of $G$. Provide three different versions and, for each version, study the computational cost of the proposed algorithms:
• (i) high-level pseudocode,
• (ii) pseudocode assuming $G$ is represented via an adjacency matrix,
• (iii) pseudocode assuming $G$ is represented using adjacency lists. #card
?
**(i) Pseudocode:**

```text
Transpose(G = (V, E))
    Initialize G^T = (V^T, E^T) as an empty graph
    for all v ∈ V do
        V^T := V^T {v}
        for all (v, u) ∈ E do
            E^T := E^T {(u, v)}
    return G^T
```

_Computational cost:_ sum of the cost of initializing the graph plus the cost of $|V| + |E|$ accesses to set elements and $|V| + |E|$ set unions.

**(ii) Adjacency matrix (**G is an **$n \times n$ matrix):**

```text
Transpose(G)
    Initialize G^T as a new n n matrix
    for i := 1 to n do
        for j := 1 to n do
            G^T[i, j] := G[j, i]
    return G^T
```

_Computational cost:_ $\Theta(n^2)$.

**(iii) Adjacency lists:
**G is an array of $n$ lists, $G[i]$ is the adjacency list (pointer to the first element) containing the identifiers of the neighbors of $i$ (the graph is directed, so neighbors are nodes $j$ for which a directed edge $(i, j)$ exists).

```text
Transpose(G)
    n := length(G)
    Initialize array G^T[1..n]
        for i := 1 to n do                   // initialize adjacency lists to empty lists
        G^T[i] := new list()
    for i := 1 to n do
            N := G[i]                            // N is the pointer to the first neighbor of i
            while N ≠q NIL do                    // traverse the neighbor list of i
                new := new node list()               // create a new node to insert into G^T
                new.val := i                         // i must be the destination node of the edge in G^T
            new.next := NIL
                insert_head(G^T[N.val], new)         // insert the new node into the adjacency list
    // // of the start node in G^T
                N := N.next                          // take the next neighbor of i
    return G^T
```

_Computational cost:_ $O(n + m)$.
