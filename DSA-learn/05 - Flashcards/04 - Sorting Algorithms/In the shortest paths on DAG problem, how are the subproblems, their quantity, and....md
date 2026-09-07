---
title: "In the shortest paths on DAG problem, how are the subproblems, their quantity, and..."
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
  - "In the shortest paths on DAG problem, how are the subproblems, their quantity, and..."
---

# 🎴 In the shortest paths on DAG problem, how are the subproblems, their quantity, and...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: In the shortest paths on DAG problem, how are the **subproblems**, their quantity, and the **recurrence relation** defined? #card

?

- **Subproblem $\textsf{dist}[v]$:** shortest distance of node $v$ from source $s$.
- **Number of subproblems:** $|V|$ (one for each node of the DAG).
- **Composition of solutions:** For a node $v$, if we know the shortest distance of all nodes $u$ that have a directed edge into $v$ ($(u,v) \in E$), we can compute:

```text
dist[v] = _{(u,v) ∈ E} { dist[u] + c(u,v) }
```

- **Resolution order:** subproblems must be solved following the **topological sort** of the nodes in the DAG.
