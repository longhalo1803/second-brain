---
title: "What is the computational cost (time complexity) of the BFS algorithm and how is i..."
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
  - "What is the computational cost (time complexity) of the BFS algorithm and how is i..."
---

# 🎴 What is the computational cost (time complexity) of the BFS algorithm and how is i...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Graph Algorithms MOC|📁 Graph Algorithms MOC]]

---

### Q: What is the computational cost (time complexity) of the BFS algorithm and how is it calculated?

````text
BFS(G, s)
    { for all u ∈ V do}
        { dist[u] := + ∈fty}
        { prev[u] := 0}
    dist[s] := 0
    Q := new_queue() // FIFO queue
    enqueue(Q, s)
    while NOT is_empty_queue(Q) do
        u := dequeue(Q)
        // optional examination of u
        for all (u, v) ∈ E do
            if dist[v] = + ∈fty then
                enqueue(Q, v)
                dist[v] := dist[u] + 1
                prev[v] := u
``` #card
?
The computational cost of BFS is **$O(|V| + |E|)$** (linear time with respect to the size of the graph).

**Proof and analysis:**

- **Node management:**
- Each node reachable from $s$ enters the queue (*enqueue*) at most **1 time** $\implies O(|V|)$.
- Each node in the queue is extracted (*dequeue*) exactly **1 time** $\implies O(|V|)$.
- Each enqueue/dequeue operation on the FIFO queue costs $\Theta(1)$.

- **Edge examination:**
- Each edge $(u,v)$ incident to a node is examined when $u$ is dequeued.
- If the graph is **directed**, each edge is considered exactly **1 time**.
- If the graph is **undirected**, each edge is considered exactly **2 times** (once from each endpoint).
- Examining the edge takes a constant number of operations $\Theta(1)$ $\implies O(|E|)$.

$$
\text{Total cost} = O(|V|) + O(|V|) + O(|E|) = O(|V| + |E|)
$$
````
