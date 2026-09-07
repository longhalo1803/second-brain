---
title: "How are the four logical steps of the Dynamic Programming algorithm for Shortest P..."
tags:
  - dsa
  - flashcards
  - clrs
  - sorting
type: reference
status: completed
created: 2026-09-25
updated: 2026-09-25
aliases:
  - "How are the four logical steps of the Dynamic Programming algorithm for Shortest P..."
---

# 🎴 How are the four logical steps of the Dynamic Programming algorithm for Shortest P...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: How are the four logical steps of the **Dynamic Programming** algorithm for Shortest Paths on DAG summarized? #card

?

1. **Solving subproblems:** computing $\textsf{dist}[v]$ for every node $v \in V$.
2. **Order from smallest to largest:** for each node $v$, the subproblems relative to nodes closer to $s$ located on paths from $s$ to $v$ have already been solved (all $\textsf{dist}[u]$ for $(u,v) \in E$).
3. **Simple composition:** the result is composed via additions and finding the minimum:

```text
dist[v] := _{(u,v) ∈ E} { dist[u] + c(u,v) }
```

4. **Precise execution order:** the solving order is strictly dictated by the **topological sort** of the DAG.
