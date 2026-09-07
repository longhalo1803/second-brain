---
title: "📘 Exercise 10.1"
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
  - "📘 Exercise 10.1"
---

# 🎴 📘 Exercise 10.1

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Graph Algorithms MOC|📁 Graph Algorithms MOC]]

---

### Q: 📘 Exercise 10.1

**Input:** Two directed graphs $G_1 = (V, E_1)$ and $G_2 = (V, E_2)$ with $V = \{1, \dots, n\}$ represented via adjacency lists.
**Output:** The union graph $G = (V, E)$ where $E = E_1 \cup E_2$, represented via adjacency lists, without modifying the input graphs and without using list primitives.

- Show an example with $n = 5$.
- Write the pseudocode of the algorithm using manual pointer manipulation for the new adjacency lists.
- Analyze the computational complexity. #card
  ?
  **Reasoning:**
  For each vertex $u \in V$, construct a new linked list containing all unique neighbors from $G_1.Adj[u]$ and $G_2.Adj[u]$. A boolean lookup array of size $n$ prevents duplicate edges in $O(1)$ check time.

**1. Example:**
$V = \{1, 2, 3, 4, 5\}$. Let $E_1 = \{(1, 2), (2, 3)\}$ and $E_2 = \{(1, 2), (1, 3), (3, 4)\}$.
Union $E = E_1 \cup E_2 = \{(1, 2), (1, 3), (2, 3), (3, 4)\}$.

**2. Pseudocode:**

```text
Algorithm GraphUnion(G_1, G_2, n):
    G ≤ftarrow new Graph with n vertices
    marked[] ≤ftarrow array of size n initialized to false
    for u ≤ftarrow 1 to n do
        G.Adj[u] ≤ftarrow NIL
        curr_1 ≤ftarrow G_1.Adj[u]
        while curr_1 ≠ NIL do
            v ≤ftarrow curr_1.dest
            if not marked[v] then
                newNode ≤ftarrow new ListNode(v, G.Adj[u])
                G.Adj[u] ≤ftarrow newNode; \; marked[v] ≤ftarrow true
            curr_1 ≤ftarrow curr_1.next
        curr_2 ≤ftarrow G_2.Adj[u]
        while curr_2 ≠ NIL do
            v ≤ftarrow curr_2.dest
            if not marked[v] then
                newNode ≤ftarrow new ListNode(v, G.Adj[u])
                G.Adj[u] ≤ftarrow newNode; \; marked[v] ≤ftarrow true
            curr_2 ≤ftarrow curr_2.next
        reset marked[v] ≤ftarrow false for all neighbors in G.Adj[u]
    return G
```

**3. Complexity:**
Iterates over all vertices and scans every edge in $E_1$ and $E_2$ once. Resetting the visited marks takes time proportional to the degree in $G$. Total time: $\Theta(|V| + |E_1| + |E_2|)$. Space complexity: $\Theta(|V| + |E_1 \cup E_2|)$ for the output graph.
