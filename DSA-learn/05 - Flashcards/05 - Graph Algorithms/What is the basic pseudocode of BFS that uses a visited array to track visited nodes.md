---
title: "What is the basic pseudocode of BFS that uses a visited array to track visited nodes"
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
  - "What is the basic pseudocode of BFS that uses a visited array to track visited nodes"
---

# 🎴 What is the basic pseudocode of BFS that uses a visited array to track visited nodes

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Graph Algorithms MOC|📁 Graph Algorithms MOC]]

---

### Q: 🟢 What is the basic pseudocode of BFS that uses a `visited` array to track visited nodes?

_Goal: check only which nodes are reachable starting from _$s$.
$G = (V,E)$ undirected/directed #card
?
Pseudocode for reachability check via BFS:

```text
BFS(G, s)
    [#24b3b3]{for all u ∈ V do}
        [#24b3b3]{visited[u] := FALSE}
    visited[s] := TRUE
    Q := new_queue() // FIFO queue
    enqueue(Q, s)
    while NOT is_empty_queue(Q) do
        u := dequeue(Q)
        // examination of u
        for all (u, v) ∈ E do
            if visited[v] = FALSE then
                enqueue(Q, v)
                visited[v] := TRUE
```

📌 Note: the `visited` array prevents inserting the same node multiple times into the queue.
📌 Note 2:
In the pseudocode above, the node is marked as visited as soon as it enters the queue (`enqueue`). This avoids inserting the same node twice into the queue.
In the following video, instead, the node is marked as visited when it is extracted from the queue (`pop`), rather than when inserted.
This is less efficient: the same node can be added to the queue multiple times before being processed (as seen at minute 4:20 where node 2 appears twice in the queue).
