---
title: "During the DFS traversal of a directed graph, what is the condition on the pre and... (3)"
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
  - "During the DFS traversal of a directed graph, what is the condition on the pre and... (3)"
---

# 🎴 During the DFS traversal of a directed graph, what is the condition on the pre and... (3)

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: During the DFS traversal of a directed graph, what is the condition on the `pre` and `post` arrays for an edge $(u,v)$ to be classified as a **Forward edge**? #card

?
An outgoing edge $(u,v)$ is classified as a **Forward edge** if and only if:

```text
pre[v] > pre[u] and post[v] > 0
```

- $\textsf{pre}[v] > \textsf{pre}[u]$: Node $v$ was discovered _after_ node $u$.
- $\textsf{post}[v] > 0$: The traversal of $v$ is already completely finished.Therefore $v$ is a **descendant** of $u$ in the DFS tree, but the edge $(u,v)$ does not belong to the spanning tree.

📝 Example:
