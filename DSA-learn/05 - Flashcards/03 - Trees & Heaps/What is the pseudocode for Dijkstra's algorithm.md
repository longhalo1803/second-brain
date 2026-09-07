---
title: "What is the pseudocode for Dijkstra's algorithm"
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
  - "What is the pseudocode for Dijkstra's algorithm"
---

# 🎴 What is the pseudocode for Dijkstra's algorithm

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: 🟢 What is the pseudocode for Dijkstra's algorithm?

$G = (V, E)$ directed/undirected
(Hint: it is best to manage the nodes using a _**priority queue**_, the most suitable data structure for this case) #card
?

```text
Dijkstra(G, c, s)
≤ft. for all u ∈ V
    dist[u] := +∈fty
    prev[u] := NIL
dist[s] := 0 } {currentColor}{[0.5ex]{5.8cm}{0.4pt}} // Initialize(G,s)
[border: 2px solid #B71C1C, 2px]{Q := Make_priority_queue({(v, dist[v]) v ∈ V})} // priority queue on dist[v]
while NOT is_empty_queue(Q) do
    [#1976D2, 2px]{u := DeQueue(Q)}      // {#D32F2F}{≤ftarrow extract min dist}
    for all (u, v) ∈ E do
        ≤ft. if dist[v] > dist[u] + c(u, v) then
            dist[v] := dist[u] + c(u, v)
            prev[v] := u
            [#D97706, 2px]{Decrease_Priority(Q, v, dist[v])} } {currentColor}{[0.5ex]{1cm}{0.4pt}} // Relax(u,v)
return prev[]
```

📌 Note:

- **`Make_priority_queue(Q')`** creates and returns a new priority queue containing the pairs of the set `Q'`.
- **`u := DeQueue(Q)`** returns the element with the highest priority (minimum value) and removes it from the queue, placing it into `u`.
- **`Decrease_Priority(Q, el, pr)`** modifies the pair `(el, pr')` in the queue by updating the priority of element `el` to a value `pr
  Dijkstra's Shortest Path Algorithm Visually Explained - Hello Byte
  Dijkstra's Shortest Path Algorithm Visually Explained | How it Works | With Examples - ByteQuest

https://algorithms-visual.com/dijkstra/ (click load to load pre-made graphs)
