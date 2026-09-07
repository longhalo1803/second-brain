---
title: "How does the Bellman-Ford algorithm detect whether a negative cycle is present in..."
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
  - "How does the Bellman-Ford algorithm detect whether a negative cycle is present in..."
---

# 🎴 How does the Bellman-Ford algorithm detect whether a negative cycle is present in...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Graph Algorithms MOC|📁 Graph Algorithms MOC]]

---

### Q: How does the Bellman-Ford algorithm detect whether a negative cycle is present in the graph? #card

?
By adding an **extra relaxation pass** (the $|V|$-th iteration) after the first $|V| - 1$ iterations:

If after the $|V| - 1$ iterations there still exists any edge $(u, v) \in E$ such that:

```text
dist[v] > dist[u] + c(u, v)
```

then there **exists a negative cycle** in the graph reachable from the source $s$.

📌 Note: in the absence of negative cycles, after $|V| - 1$ iterations all distances are stable and no further relaxation can decrease any $\textsf{dist}$ value.
