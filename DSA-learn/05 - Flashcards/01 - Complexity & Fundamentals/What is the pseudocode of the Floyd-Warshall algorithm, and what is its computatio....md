---
title: "What is the pseudocode of the Floyd-Warshall algorithm, and what is its computatio..."
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
  - "What is the pseudocode of the Floyd-Warshall algorithm, and what is its computatio..."
---

# 🎴 What is the pseudocode of the Floyd-Warshall algorithm, and what is its computatio...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Complexity & Fundamentals MOC|📁 Complexity & Fundamentals MOC]]

---

### Q: 🟢 What is the pseudocode of the Floyd-Warshall algorithm, and what is its computational and space complexity? #card

?
**Pseudocode:**

```text
Floyd-Warshall(G, c)
    for i := 1 to n do
        for j := 1 to n do
            if i = j then dist[i, j, 0] := 0
            else dist[i, j, 0] := +∈fty
    for all (i, j) ∈ E do                // {#D9534F}{≤ftarrow Initialization: O(n^2)}
        dist[i, j, 0] := c(i, j)
    for k := 1 to n do
        for i := 1 to n do                   // {#D9534F}{≤ftarrow 3 nested loops: O(n^3)}
            for j := 1 to n do
                dist[i, j, k] := ≤ft( dist[i, j, k-1],
dist[i, k, k-1] + dist[k, j, k-1] )  // {#D9534F}{≤ftarrow O(1)}
    return dist[, , n]
```

**Complexity:**

- **Time:** $O(n^3)$, due to the three nested for loops from $1$ to $n$, each with an $O(1)$ body.
- **Space:** $O(n^3)$ if all matrices are stored, reducible to $O(n^2)$ because the computation of step $k$ only requires values from step $k-1$ (and the update can be performed in-place on the same matrix).

https://algoanim.ide.sk/index.php?page=showanim&id=50 (https://www.cs.usfca.edu/~galles/JavascriptVisual/Floyd.html, https://cuuduongthancong.com/~galles/visualization/Floyd.html)
