---
title: "Explain how the edges of a directed graph can be classified based on the pre and p..."
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
  - "Explain how the edges of a directed graph can be classified based on the pre and p..."
---

# 🎴 Explain how the edges of a directed graph can be classified based on the pre and p...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: ❓ Explain how the edges of a directed graph can be classified based on the pre and post timestamps of a DFS traversal. #card

?
During depth-first search (DFS) on a directed graph $G=(V, E)$, each vertex $u$ is assigned two timestamps:

- $pre[u]$: the time when $u$ is first discovered.
- $post[u]$: the time when exploration of all descendants of $u$ is completed.The time interval $[pre[u], post[u]]$ describes the lifespan of the node on the recursion stack. Based on how intervals of endpoints nest, any directed edge $(u, v) \in E$ falls into one of the following four categories:
- **Tree Edges:**
  Edges belonging to the DFS forest, through which an unvisited vertex $v$ is discovered.
  The interval of $v$ is strictly contained within that of $u$:

$$

pre[u] < pre[v] < post[v] < post[u]

$$

- **Forward Edges:**
  Edges connecting an ancestor node $u$ to a non-immediate descendant $v$ in the DFS forest.
  The time interval satisfies the same inclusion relationship as tree edges:

$$

pre[u] < pre[v] < post[v] < post[u]

$$

_(Distinguished from tree edges because when the edge is explored, *$v$* has already been marked as visited)._

- **Back Edges:**
  Edges connecting a vertex $u$ to an ancestor $v$ in the DFS tree (including self-loops).
  The interval of $u$ is entirely contained within that of $v$:

$$

pre[v] < pre[u] < post[u] < post[v]

$$

_(The presence of at least one back edge is a necessary and sufficient condition for the existence of directed cycles)._

- **Cross Edges:**
  Edges connecting nodes that are neither ancestors nor descendants of each other (connecting different branches of the same tree or separate trees).
  The exploration of node $v$ finished completely before that of $u$ began:

$$

pre[v] < post[v] < pre[u] < post[u]

$$

_(In a directed graph, edges with *$pre[u] < post[u] < pre[v] < post[v]$* can never exist)._
