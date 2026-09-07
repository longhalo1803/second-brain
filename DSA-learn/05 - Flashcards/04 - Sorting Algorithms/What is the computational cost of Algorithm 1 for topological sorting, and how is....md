---
title: "What is the computational cost of Algorithm 1 for topological sorting, and how is..."
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
  - "What is the computational cost of Algorithm 1 for topological sorting, and how is..."
---

# 🎴 What is the computational cost of Algorithm 1 for topological sorting, and how is...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: What is the computational cost of Algorithm 1 for topological sorting, and how is an efficient implementation achieved? #card

?
With a suitable data structure, the computational cost is **$O(|V| + |E|)$**.

Efficient implementation:

- The $\textsf{in-degree}$ of each node is stored in an array.
- All nodes with $\text{in-degree} = 0$ are inserted into an initial queue (or stack).
- While the queue is not empty:
- A node $u$ is extracted from the queue and added to the ordering.
- For each outgoing edge $(u,v) \in E$, the $\text{in-degree}$ of $v$ is decremented.
- If the $\text{in-degree}$ of $v$ becomes 0, $v$ is inserted into the queue.
  📌 Note: an unoptimized sequential search for a source at each step would require $O(|V|)$ time, leading to a total complexity of $O(|V|^2)$.
