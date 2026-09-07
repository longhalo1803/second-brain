---
title: "What is the complete pseudocode of the BFS algorithm for computing distances from..."
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
  - "What is the complete pseudocode of the BFS algorithm for computing distances from..."
---

# 🎴 What is the complete pseudocode of the BFS algorithm for computing distances from...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: 🟢 What is the complete pseudocode of the BFS algorithm for computing distances from the root and the spanning tree?

_Goal: compute the shortest distance (in number of edges) from *$s$* and reconstruct shortest paths._
$G = (V,E)$ undirected/directed #card
?
• **Distance **between $u$ and $v$:
number of edges on the shortest path
in $G$ between $u$ and $v$.
• **`dist[u]`** stores the distance
from $s$ to $u$.
• **`prev[u]`** stores the
predecessor (parent) of $u$ in the spanning tree
from the BFS traversal
with source $s$. `prev[u]=0` means "`u` _has no predecessor_"

Complete pseudocode of BFS with `dist[]` and `prev[]`:

```text
BFS(G, s)
    [#24b3b3]{for all u ∈ V do}
        [#24b3b3]{dist[u] := + ∈fty}
        [#24b3b3]{prev[u] := NIL}
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
```

📌 Note: the array `dist[]` completely replaces `visited[]`: a node $v$ is already visited/discovered if and only if $\text{dist}[v] \neq +\infty$.
In practice, $+\infty$ can be replaced
with any value $> n$.
