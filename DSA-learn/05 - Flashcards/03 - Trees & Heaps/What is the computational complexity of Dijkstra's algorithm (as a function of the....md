---
title: "What is the computational complexity of Dijkstra's algorithm (as a function of the..."
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
  - "What is the computational complexity of Dijkstra's algorithm (as a function of the..."
---

# 🎴 What is the computational complexity of Dijkstra's algorithm (as a function of the...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: What is the computational complexity of Dijkstra's algorithm (as a function of the priority queue primitives)?

````text
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
``` #card
?
The complexity of Dijkstra's algorithm depends on the number of calls to the primitives of the **Priority Queue **$Q$ and on their respective costs:

- **Initialization:** $O(|V|)$ to create the $\textsf{dist}$ and $\textsf{prev}$ arrays + cost of $\textsf{Make_priority_queue}$;
- **Extract-min (**$\textsf{DeQueue}$**):** executed exactly $|V|$ times (once for each node);
- **Update priority (**$\textsf{Decrease_Priority}$**):** executed at most $|E|$ times (once for each edge).
**Total complexity:**

```text
O(|V| + |E|) + cost of Make_priority_queue + |V| T_{DeQueue} + |E| T_{Decrease_Priority}
````

📌 Examples of complexity based on the data structure used for $Q$:

- **Unordered Array / List:** $T_{\textsf{DeQueue}} = O(|V|)$, $T_{\textsf{Decrease}} = O(1)$ $\implies O(|V|^2)$;
- **Binary Heap:** $T_{\textsf{DeQueue}} = O(\log |V|)$, $T_{\textsf{Decrease}} = O(\log |V|)$ $\implies O((|V| + |E|) \log |V|)$;
- **Fibonacci Heap:** $T_{\textsf{DeQueue}} = O(\log |V|)$, $T_{\textsf{Decrease}} = O(1)$ amortized $\implies O(|E| + |V| \log |V|)$.
