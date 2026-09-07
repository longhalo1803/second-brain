---
title: "Describe the Priority Queue data structure and explain how it is used in Prim's al..."
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
  - "Describe the Priority Queue data structure and explain how it is used in Prim's al..."
---

# 🎴 Describe the Priority Queue data structure and explain how it is used in Prim's al...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: ❓ Describe the Priority Queue data structure and explain how it is used in Prim's algorithm for constructing a Minimum Spanning Tree. #card

?

- **Priority Queue Data Structure (Min-Priority Queue):**
  An abstract data structure that manages a dynamic set of elements with associated keys (priorities), supporting the following operations:
- `Insert(Q, x)`: inserts an element $x$ into the queue.
- `Extract-Min(Q)`: extracts and removes the element with the minimum key.
- `Decrease-Key(Q, x, k)`: decreases the value of the key associated with element $x$ to the new value $k \le \text{key}(x)$. Typically implemented using a min-heap, it supports `Extract-Min` and `Decrease-Key` in $\mathcal{O}(\log n)$ time.
- **Use of the Priority Queue in Prim's Algorithm:**
  Prim's algorithm builds the MST by growing a single tree starting from an arbitrary root $r$. The priority queue $Q$ holds all vertices that **do not yet belong to the tree**:
- **Initialization:** For each vertex $v \in V$, key $key[v]$ represents the minimum weight among all edges connecting $v$ to nodes already in the tree. Initially set $key[v] = \infty$ for all $v \ne r$, and $key[r] = 0$. All nodes are inserted into $Q$.
- **Extracting the closest vertex:** In each iteration, call `Extract-Min(Q)`. This extracts vertex $u \notin T$ that has the light connecting edge to the current tree $T$. Node $u$ joins the tree via edge $(parent[u], u)$.
- **Updating neighbors (`Decrease-Key`):** For each adjacent vertex $v$ of $u$ that is still in $Q$: if the edge weight $w(u, v)$ is less than current $key[v]$, the newly added node $u$ offers a cheaper connection to the tree than previously found. Update $parent[v] = u$ and call `Decrease-Key(Q, v, w(u, v))` to update the priority of $v$ inside the queue. Using a priority queue ensures that light edge selection runs in logarithmic time, yielding an overall complexity for Prim of $\mathcal{O}(|E| \log |V|)$ using a binary heap.
