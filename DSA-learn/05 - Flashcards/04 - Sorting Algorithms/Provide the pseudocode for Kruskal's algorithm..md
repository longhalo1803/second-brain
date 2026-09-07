---
title: "Provide the pseudocode for Kruskal's algorithm."
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
  - "Provide the pseudocode for Kruskal's algorithm."
---

# 🎴 Provide the pseudocode for Kruskal's algorithm.

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: 🟢 Provide the pseudocode for Kruskal's algorithm. #card

?

```text
Kruskal(G = (V, E), c)
    S := make_set(V)                     // Initialize Disjoint Set for each node
    T := new_list()                      // Tree edge list
    sort the edges of E in non-decreasing order of cost c
    count := 0
    while count make_set(V): creates a disjoint set (Union-Find) for each vertex. Cost: $\mathcal{O}(|V|)$.

- sort E: sorts edges in ascending order of cost. Dominant cost: $\mathcal{O}(|E| \log |E|)$.



- **Phase 2: Greedy Loop**


- Iterates through the sorted edges until $|V| - 1$ edges are selected (a tree with $\vert{}V\vert{}$ vertices always has exactly $\vert{}V\vert{} - 1$ edges).

- find-set(S, u) != find-set(S, v): checks if the nodes belong to distinct components. If so, the edge does not form cycles. Cost: $\mathcal{O}(\log |V|)$.

- union(S, u, v): merges the two components into a single set. Cost: $\mathcal{O}(\log |V|)$.



- **Total Complexity:** $\mathcal{O}(|E| \log |V|)$.

**📝 Example:**

Consider 4 nodes $\{A, B, C, D\}$ and edges sorted by cost: $(A,B): 1$, $(B,C): 2$, $(A,C): 3$.


- Initial state: $\{A\}, \{B\}, \{C\}, \{D\}$

- Examine $(A,B)$: find(A) != find(B) $\rightarrow$ Pick $(A,B)$ and merge the two components. Sets: $\{A,B\}, \{C\}, \{D\}$.

- Examine $(B,C)$: find(B) != find(C) $\rightarrow$ Pick $(B,C)$ and merge the two components. Sets: $\{A,B,C\}, \{D\}$.

- Examine $(A,C)$: find(A) == find(C) $\rightarrow$ **Cycle detected!** Discard $(A,C)$.

📌 Note:
The function `find-set(S, x)` essentially starts from node $x$ and traverses up the parent chain until it finds the root of the set containing $x$, returning that root element.
When the algorithm examines an edge connecting node $u$ and node $v$:It executes `find-set(S, u)`  $\rightarrow$ finds the root of $u$'s set.It executes `find-set(S, v)` $\rightarrow$ finds the root of $v$'s set.At that point:
- If the two roots are different (`find-set(u) != find-set(v)`):
- The two nodes belong to two different, separate trees/components. Connecting them does not create a cycle (you are merging two distinct components).
- If the two roots coincide (`find-set(u) == find-set(v)`):
- The two nodes are already in the same component (there was already a path connecting them). Adding a direct edge between them closes the loop and creates a cycle, so the edge must be discarded.

https://algorithms-visual.com/kruskal/ (click load to load pre-made graphs)
```
