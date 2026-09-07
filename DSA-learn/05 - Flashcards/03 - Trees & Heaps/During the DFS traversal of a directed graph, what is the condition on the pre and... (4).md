---
title: "During the DFS traversal of a directed graph, what is the condition on the pre and... (4)"
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
  - "During the DFS traversal of a directed graph, what is the condition on the pre and... (4)"
---

# 🎴 During the DFS traversal of a directed graph, what is the condition on the pre and... (4)

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: During the DFS traversal of a directed graph, what is the condition on the `pre` and `post` arrays for an edge $(u,v)$ to be classified as a **Cross edge**? #card

?
An outgoing edge $(u,v)$ is classified as a **Cross edge** if and only if:

```text
0  0$: The traversal of node $v$ is already finished.
- $\textsf{post}[v] < \textsf{pre}[u]$: The traversal of $v$ finished *before* the traversal of $u$ even started.Consequently, $v$ is neither an ancestor nor a descendant of $u$ (it lies in another branch of the tree or in another tree of the DFS forest).

📝 Example:
```
