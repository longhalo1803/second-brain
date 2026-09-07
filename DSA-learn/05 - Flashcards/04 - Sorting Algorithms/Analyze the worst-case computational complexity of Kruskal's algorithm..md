---
title: "Analyze the worst-case computational complexity of Kruskal's algorithm."
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
  - "Analyze the worst-case computational complexity of Kruskal's algorithm."
---

# 🎴 Analyze the worst-case computational complexity of Kruskal's algorithm.

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: Analyze the worst-case computational complexity of Kruskal's algorithm. #card

?

- **Disjoint Set Initialization (`make_set`):** $O(|V|)$.
- **Edge Sorting:** Sorting $|E|$ edges requires $O(|E| \log |E|)$ time.
- **`while` Loop:** Executed at most $|E|$ times (once for each edge in sorted order):
- Executes 2 `find-set` operations and possibly 1 `union` operation.
- With standard Disjoint Set heuristics, each of these operations takes $O(\log |V|)$ time.
- Total for the loop: $O(|E| \log |V|)$.

```text
Kruskal(G = (V, E), c)
    S := make_set(V)                     // Disjoint Set {#D9534F}{O(|V|)}
    T := new_list()                      // {#D9534F}{O(1)}
    sort the edges of E in non-decreasing order of cost c // {#D9534F}{O(|E| |E|)}
    count := 0
    while count < |V| - 1 do             // executed at most |E| times
        choose the next edge (u,v) ∈ E in the sorted order
        if find-set(S, u) ≠q find-set(S, v) then // {#D9534F}{O( |V|)}
            p := new_list_node()
            p.val := (u,v)
            insert-head(T, p)
            union(S, u, v)                       // {#D9534F}{O( |V|)}
            count := count + 1
    return T
```

**Total Complexity:**

$$
O(|V|) + O(|E| \log |E|) + O(|E| \log |V|) = O(|E| \log |E|) = O(|E| \log |V|)
$$

📌 **Note on the relationship between $\log |E|$ and $\log |V|$:**
Since the graph has at most $|E| \leq |V|^2$ edges, we have:

$$
\log |E| \leq \log (|V|^2) = 2 \log |V| \implies O(\log |E|) = O(\log |V|)
$$

Thus, the final complexity of Kruskal's algorithm is commonly expressed as:

```text
O(|E| |V|) or O(|E| |E|)
```
