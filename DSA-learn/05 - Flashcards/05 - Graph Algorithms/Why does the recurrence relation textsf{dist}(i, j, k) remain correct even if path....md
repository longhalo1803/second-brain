---
title: "Why does the recurrence relation textsf{dist}(i, j, k) remain correct even if path..."
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
  - "Why does the recurrence relation textsf{dist}(i, j, k) remain correct even if path..."
---

# 🎴 Why does the recurrence relation textsf{dist}(i, j, k) remain correct even if path...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Graph Algorithms MOC|📁 Graph Algorithms MOC]]

---

### Q: Why does the recurrence relation $\textsf{dist}(i, j, k)$ remain correct even if paths i → k and k → j share an intermediate vertex w? #card

?
If the two shortest subpaths $i \leadsto k$ and $k \leadsto j$ were to share an intermediate node $w \in \{1, \dots, k-1\}$, concatenating them would create a cycle passing through $w$ and $k$.

However:

- Since the graph **contains no negative-cost cycles**, the total cost of the cycle cannot be strictly negative (it is $\ge 0$).
- Therefore, there exists an alternative direct path from $i$ to $j$ that passes through $w$ **without visiting $k$**, whose length is less than or equal to the sum:

```text
length(i ≤adsto w ≤adsto j) ≤ dist(i, k, k-1) + dist(k, j, k-1)
```

- This alternative path uses only nodes in $\{1, \dots, k-1\}$ and is therefore already covered by the definition of $\textsf{dist}(i, j, k-1)$. Consequently:

```text
dist(i, j, k-1) ≤ dist(i, k, k-1) + dist(k, j, k-1)
```

The $\min$ function will therefore choose $\textsf{dist}(i, j, k-1)$, discarding the cyclic composition and preserving the correctness of the optimal value.
