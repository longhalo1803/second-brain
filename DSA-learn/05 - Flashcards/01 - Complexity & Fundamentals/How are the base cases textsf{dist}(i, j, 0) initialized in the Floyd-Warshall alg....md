---
title: "How are the base cases textsf{dist}(i, j, 0) initialized in the Floyd-Warshall alg..."
tags:
  - dsa
  - flashcards
  - clrs
  - complexity
type: reference
status: completed
created: 2026-09-25
updated: 2026-09-25
aliases:
  - "How are the base cases textsf{dist}(i, j, 0) initialized in the Floyd-Warshall alg..."
---

# 🎴 How are the base cases textsf{dist}(i, j, 0) initialized in the Floyd-Warshall alg...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Complexity & Fundamentals MOC|📁 Complexity & Fundamentals MOC]]

---

### Q: How are the base cases $\textsf{dist}(i, j, 0)$ initialized in the Floyd-Warshall algorithm? #card

?
The base case corresponds to $k = 0$, that is, finding paths from $i$ to $j$ that use **no intermediate nodes** ($\textsf{dist}(i, j, 0)$). The path can therefore consist solely of a single direct edge or the empty path:

```text
dist(i, j, 0) = {cases} 0            // if i = j
c(i, j)                              // if i ≠q j (i, j) ∈ E
+∈fty                                // if i ≠q j (i, j) E {cases}
```

**Meaning of the three cases:**

- **Distance from a node to itself ($i = j$):** it is always $0$ (in the absence of negative cycles).
- **Existence of a direct edge:** if the edge $(i, j)$ exists, the shortest distance without intermediate nodes equals the cost $c(i, j)$.
- **Absence of a direct edge ($(i, j) \notin E$):** since no intermediate nodes can be traversed, the destination is unreachable ($+\infty$).📝 Example:
  If there is a directed edge from node 1 to node 4 with weight 1, then $\textsf{dist}(1, 4, 0) = 1$. If there is no direct edge between node 2 and node 4, $\textsf{dist}(2, 4, 0) = +\infty$.
