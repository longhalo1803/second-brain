---
title: "What does the relaxation operation of an edge (u, v) consist of in Dijkstra's algo..."
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
  - "What does the relaxation operation of an edge (u, v) consist of in Dijkstra's algo..."
---

# 🎴 What does the relaxation operation of an edge (u, v) consist of in Dijkstra's algo...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: What does the _relaxation_ operation of an edge $(u, v)$ consist of in Dijkstra's algorithm? #card

?
The relaxation operation checks whether the path to node $v$ passing through node $u$ is shorter than the best currently known path to $v$.

```text
if dist[v] > dist[u] + c(u,v) then
    dist[v] := dist[u] + c(u,v)
    prev[v] := u
```

If the condition holds, the estimated distance for $v$ is reduced and its parent in the shortest path tree is updated to $u$.

📝 Example:
**Initial path**: passes through node $A$ ($S \to A \to v$) with a total cost of $8 + 6 = 14$. This value is initially stored as `dist[v] = 14`.
**New path**: passes through node $u$ ($S \to u \to v$). The cost to reach $u$ is `dist[u] = 4` and the weight of edge $(u, v)$ is $c(u,v) = 3$. The total cost via $u$ is $4 + 3 = 7$.
**Relaxation**: since $14 > 7$, the estimated value of `dist[v]` is updated to 7 and the predecessor node `prev[v]` is set to `u`.
