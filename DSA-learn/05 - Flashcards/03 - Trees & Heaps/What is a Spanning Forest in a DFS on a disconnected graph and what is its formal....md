---
title: "What is a Spanning Forest in a DFS on a disconnected graph and what is its formal..."
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
  - "What is a Spanning Forest in a DFS on a disconnected graph and what is its formal..."
---

# 🎴 What is a Spanning Forest in a DFS on a disconnected graph and what is its formal...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: What is a Spanning Forest in a DFS on a disconnected graph and what is its formal definition? #card

?
If the graph $G = (V, E)$ is **disconnected**, a single DFS traversal from a node cannot reach all vertices. The DFS will then perform a distinct traversal for each connected component, generating a **Spanning Forest**.

**Formal definition:**
A spanning forest is a set of spanning trees $\{T_1 = (V_1, E_1), T_2 = (V_2, E_2), \dots, T_k = (V_k, E_k)\}$ such that:

- Each $T_i$ is a subgraph of $G$;
- Each $T_i$ is a tree that spans a connected component of $G$;
- The vertices of the trees are disjoint and their union spans the entire set of vertices of $G$:

```text
_{i=1}^k V_i = V with V_i V_j = \; i ≠q j
```

📌 Note: the number of trees $k$ in the forest coincides exactly with the **number of connected components** of the graph $G$.
