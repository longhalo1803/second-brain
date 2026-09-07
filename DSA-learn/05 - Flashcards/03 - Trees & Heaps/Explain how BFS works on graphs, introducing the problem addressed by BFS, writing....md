---
title: "Explain how BFS works on graphs, introducing the problem addressed by BFS, writing..."
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
  - "Explain how BFS works on graphs, introducing the problem addressed by BFS, writing..."
---

# 🎴 Explain how BFS works on graphs, introducing the problem addressed by BFS, writing...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: ❓ Explain how BFS works on graphs, introducing the problem addressed by BFS, writing and commenting on the pseudocode. How can BFS be used to compute the single-source shortest path tree when all edge weights are equal? (When and why can BFS be used to compute the single-source shortest path tree?) #card

?

- **Problem addressed:**
  Breadth-First Search (BFS) systematically explores the vertices of a graph $G=(V,E)$ starting from a source $s$, visiting all nodes at distance $k$ from $s$ before exploring any node at distance $k+1$. It solves the problem of finding the shortest distance (in terms of number of edges) from $s$ to all reachable nodes.
- **Pseudocode and commentary:**`BFS(G, s):
  for each u in V - {s}:
      color[u] = WHITE        // unvisited
      d[u] = INFINITY         // distance from s
      pi[u] = NIL             // predecessor in BFS tree
  color[s] = GRAY             // visited but not finished
  d[s] = 0
  pi[s] = NIL
  Q = EmptyQueue()
  Enqueue(Q, s)               // FIFO management
  while Q is not empty:
      u = Dequeue(Q)
      for each v in Adjacent[u]:
          if color[v] == WHITE:
              color[v] = GRAY
              d[v] = d[u] + 1
              pi[v] = u
              Enqueue(Q, v)
      color[u] = BLACK        // exploration finished
`_Commentary_: The fundamental data structure is the **FIFO** queue $Q$. It ensures that nodes are dequeued strictly in order of their distance from $s$. Colors prevent redundant re-explorations and infinite loops.
- **Use for shortest paths with equal edge weights:**
- **When:** When the graph has uniform edge weights (e.g., all edges have unit weight or the same constant $c > 0$).
- **Why:** Since the FIFO queue guarantees that vertices are discovered and queued in increasing order of their distance from $s$ ($d[v]$ is non-decreasing in the queue), the first time a white node $v$ is reached via an edge $(u, v)$ identifies the path with the minimum number of edges. Since all edge weights equal $c$, the weighted cost of a path of $k$ edges is simply $k \cdot c$. Consequently, minimizing the number of edges is equivalent to minimizing the overall weighted distance. The pointers $\pi[v]$ directly define the shortest path tree.
