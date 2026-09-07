---
title: "📘 Exercise 31.2"
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
  - "📘 Exercise 31.2"
---

# 🎴 📘 Exercise 31.2

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: 📘 Exercise 31.2

**Input:** A directed graph $G = (V, E)$ with $V = \{1, \dots, n\}$ and a source vertex $s \in V$.
**Output:** Print the identifiers of a directed cycle in $G$ containing $s$ in the order they appear along the cycle, or print "non esiste" if no such cycle exists.

- Show an example with $n \ge 5$ where such a cycle exists.
- Describe an algorithm in words and provide pseudocode.
- Analyze its computational complexity. #card
  ?
  **Reasoning:**
  A directed cycle containing $s$ exists if and only if there is a directed path from some out-neighbor $v \in Adj[s]$ back to $s$. We can find the shortest such path by initiating a Breadth-First Search (BFS) starting at $s$, treating $s$ initially as unvisited so that it can be reached again by an incoming edge from one of its descendants.

**1. Example:**
Let $V = \{1, 2, 3, 4, 5\}$, with $s = 1$.
Edges: $(1, 2), (2, 3), (3, 4), (4, 1), (3, 5)$.
Cycle containing $1$: $1 \to 2 \to 3 \to 4 \to 1$. Output: 1, 2, 3, 4, 1.

**2. Algorithm Description:**
Initialize a $visited$ array to false and a $parent$ array to NIL. Enqueue each neighbor $v \in Adj[s]$, marking $visited[v] \leftarrow \text{true}$ and $parent[v] \leftarrow s$. Run BFS standard traversal; if vertex $s$ is ever discovered as an outgoing neighbor of some node $u$, record $parent[s] \leftarrow u$, stop the search, and trace parent pointers backwards from $s$ to reconstruct the cycle. If the queue empties without encountering $s$, print "non esiste".

**3. Pseudocode:**

```text
Algorithm FindCycleContainingS(G, s, n):
    visited[] ≤ftarrow array of size n initialized to false
    parent[] ≤ftarrow array of size n initialized to NIL
    Q ≤ftarrow new_queue()
    found ≤ftarrow false
    for each v ∈ Adj[s] do
        if v = s then
            print (s, s); \; return
        visited[v] ≤ftarrow true; \; parent[v] ≤ftarrow s
        enqueue(Q, v)
    while not is_empty(Q) not found do
        u ≤ftarrow dequeue(Q)
        for each w ∈ Adj[u] do
            if w = s then
                parent[s] ≤ftarrow u; \; found ≤ftarrow true
            else if not visited[w] then
                visited[w] ≤ftarrow true; \; parent[w] ≤ftarrow u
                enqueue(Q, w)
    if not found then
        print "non esiste"
    else
        ReconstructAndPrintForward(s, parent)
```

**4. Complexity:**

- Time Complexity: $O(|V| + |E|)$, as each vertex and edge reachable from $s$ is processed at most once.
- Space Complexity: $O(|V|)$ for the queue, parent, and visited arrays.
