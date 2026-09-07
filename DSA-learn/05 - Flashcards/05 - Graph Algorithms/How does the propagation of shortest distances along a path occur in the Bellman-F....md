---
title: "How does the propagation of shortest distances along a path occur in the Bellman-F..."
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
  - "How does the propagation of shortest distances along a path occur in the Bellman-F..."
---

# 🎴 How does the propagation of shortest distances along a path occur in the Bellman-F...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Graph Algorithms MOC|📁 Graph Algorithms MOC]]

---

### Q: How does the propagation of shortest distances along a path occur in the Bellman-Ford algorithm? #card

?
Let

$$
(s) \to (u_1) \to (u_2) \to \dots \to (u_k) \to (v)
$$

be a shortest path from $s$ to $v$:

- **Initially:** only $\textsf{dist}[s] = 0$, while all other nodes have distance $+\infty$.
- **Iteration 1:** the edge $(s, u_1)$ is relaxed correctly, establishing the final shortest distance for $u_1$ and setting $\textsf{prev}[u_1] = s$.
- **Iteration 2:** with $\textsf{dist}[u_1]$ correct, the relaxation of edge $(u_1, u_2)$ determines the final shortest distance for $u_2$ and sets $\textsf{prev}[u_2] = u_1$.
- **Iteration $i$:** the shortest distance is determined for node $u_i$, which is $i$ edges away from $s$.
  At each iteration, knowledge of shortest distances propagates "forward" by at least one edge along each shortest path.
