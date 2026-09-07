---
title: "During the DFS traversal of a directed graph, what is the condition on the pre and... (2)"
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
  - "During the DFS traversal of a directed graph, what is the condition on the pre and... (2)"
---

# 🎴 During the DFS traversal of a directed graph, what is the condition on the pre and... (2)

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: During the DFS traversal of a directed graph, what is the condition on the `pre` and `post` arrays for an edge $(u,v)$ to be classified as a **Back edge**? #card

?
An outgoing edge $(u,v)$ is classified as a **Back edge** if and only if:

```text
pre[v] < pre[u] and post[v] = 0
```

- $\textsf{pre}[v] < \textsf{pre}[u]$: The traversal of node $v$ started _before_ that of node $u$.
- $\textsf{post}[v] = 0$: The traversal of node $v$ has not finished yet (it is currently on the recursion stack).Consequently, $v$ is an **ancestor** of $u$. The edge $(u,v)$ allows traversing back up the DFS tree, forming a directed cycle!

⚠️ Warning: the presence of a back edge identifies the presence of a cycle in the graph.

📝 Example:

📌 Note:

Even an edge that goes directly back to the parent, that is, the inverse of the corresponding tree edge, is a back edge:
