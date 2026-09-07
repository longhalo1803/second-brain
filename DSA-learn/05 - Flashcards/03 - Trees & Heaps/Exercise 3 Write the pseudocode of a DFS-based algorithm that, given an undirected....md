---
title: "Exercise 3 Write the pseudocode of a DFS-based algorithm that, given an undirected..."
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
  - "Exercise 3 Write the pseudocode of a DFS-based algorithm that, given an undirected..."
---

# 🎴 Exercise 3 Write the pseudocode of a DFS-based algorithm that, given an undirected...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: 📝 Exercise 3: Write the pseudocode of a DFS-based algorithm that, given an undirected graph $G=(V,E)$ as input, determines the connected components of $G$ by associating each node in the array `cc[1..n]` with the integer identifier (ID) of the component to which it belongs.

💡 HintUse an array `cc[1..n]` initialized to 0 (0 = not analyzed). Instead of the `visited` array, we use `cc[v] == 0` to recognize unvisited nodes, and assign `cc[v] = id` during traversal. #card
?
The algorithm assigns each node the identifier `id` of the component it belongs to.

```text
CC(G)
    cc[0..n] new array
    for all v ∈ V do
        cc[v] := 0                           // 0 indicates not yet analyzed
    id := 0
    for all v ∈ V do
        if cc[v] = 0 then
            id := id + 1                         // new component identifier
            CC-Visit(G, v, id)
    return cc

CC-Visit(G, v, id)
    {aligned}                            // cc[v] := id
    // for all (v, u) ∈ E do
        // if cc[u] = 0 then
            // CC-Visit(G, u, id){aligned}
```

**Computational cost:** $O(|V| + |E|)$.

📌 Note:
At the end of execution, two nodes $u$ and $v$ belong to the same connected component if and only if $\textsf{cc}[u] == \textsf{cc}[v]$.
