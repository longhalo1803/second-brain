---
title: "During the DFS traversal of a directed graph, what is the condition on the pre and..."
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
  - "During the DFS traversal of a directed graph, what is the condition on the pre and..."
---

# 🎴 During the DFS traversal of a directed graph, what is the condition on the pre and...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: During the DFS traversal of a directed graph, what is the condition on the `pre` and `post` arrays for an edge $(u,v)$ to be classified as a **Tree edge**? #card

?
An outgoing edge $(u,v)$ is classified as a **Tree edge** if and only if:

```text
pre[v] = 0
```

Node $v$ has not yet been discovered (its start time is 0) and is discovered for the first time precisely through the exploration of edge $(u,v)$.

📝 Example:
