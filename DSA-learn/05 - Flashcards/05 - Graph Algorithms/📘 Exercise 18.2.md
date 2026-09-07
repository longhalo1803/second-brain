---
title: "📘 Exercise 18.2"
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
  - "📘 Exercise 18.2"
---

# 🎴 📘 Exercise 18.2

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Graph Algorithms MOC|📁 Graph Algorithms MOC]]

---

### Q: 📘 Exercise 18.2

**Input:** A directed graph $G = (V, E)$ of $n \ge 3$ vertices ($V = \{1, \dots, n\}$), and three vertices $u, v, w \in V$.
**Output:** The nodes on the shortest path from $u$ to $v$ that DOES NOT pass through $w$ (in correct order), or print "no path exists".

Explain the algorithm, provide pseudocode using high-level graph representation, and analyze computational complexity. #card
?
**Reasoning:**
Since the path cannot use $w$, vertex $w$ is simply treated as inaccessible (deleted or permanently marked as visited). Running BFS from $u$ finds the shortest unweighted path to $v$. Parent pointers enable reconstructing the path.

**Algorithm Description:**
Initialize a $visited$ array to false and a $parent$ array to NIL. Set $visited[w] \leftarrow \text{true}$ so $w$ is never explored. Start BFS from $u$. If $v$ is reached, trace parent pointers backwards from $v$ to $u$, reverse the list, and print the path. If BFS terminates without reaching $v$, print "no path exists".

**Pseudocode:**

```text
Algorithm ShortestPathAvoidingW(G, u, v, w):
    if u = w v = w then
        print "no path exists"; \; return
    visited[] ≤ftarrow array of false of size |V|
    parent[] ≤ftarrow array of NIL of size |V|
    visited[w] ≤ftarrow true; \; visited[u] ≤ftarrow true
    Q ≤ftarrow new_queue(); \; enqueue(Q, u)
    while not is_empty(Q) not visited[v] do
        curr ≤ftarrow dequeue(Q)
        for each neighbor ∈ Adj[curr] do
            if not visited[neighbor] then
                visited[neighbor] ≤ftarrow true
                parent[neighbor] ≤ftarrow curr
                enqueue(Q, neighbor)
    if not visited[v] then
        print "no path exists"
    else
        PrintPathReversed(v, parent)
```

**Complexity:**
BFS processes at most $|V|$ vertices and $|E|$ edges: $O(|V| + |E|)$ time and $O(|V|)$ auxiliary space.
