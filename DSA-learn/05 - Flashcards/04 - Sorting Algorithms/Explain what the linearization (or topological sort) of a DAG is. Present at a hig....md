---
title: "Explain what the linearization (or topological sort) of a DAG is. Present at a hig..."
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
  - "Explain what the linearization (or topological sort) of a DAG is. Present at a hig..."
---

# 🎴 Explain what the linearization (or topological sort) of a DAG is. Present at a hig...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: ❓ Explain what the linearization (or topological sort) of a DAG is. Present at a high level (no code) the DFS-based algorithm seen previously for linearization, and explain why it is correct. #card

?

- **Definition of Topological Sort:**
  A topological sort of a DAG $G=(V,E)$ is a linear arrangement of the vertices such that if there exists an edge $(u, v) \in E$, then $u$ precedes $v$ in the sequence.
- **DFS-based Algorithm (high level):**
- Perform a standard depth-first search (DFS) on the entire graph, keeping track of vertex finishing times (the `post` time or return from recursion).
- As each vertex finishes its DFS visit (becoming "black" / recording its `post` time), prepend it to a linked list (or push it onto a stack).
- Upon completing the DFS on all vertices, the resulting list contains the vertices sorted in descending order of their finishing times (`post-visit`). This list represents the topological sort.
- **Proof of Correctness:**
  We must show that for every edge $(u, v) \in E$, $u$ finishes after $v$, i.e., $post[u] > post[v]$.
  When DFS explores edge $(u, v)$, three possible states can occur for $v$:
- **$v$ is Gray (currently being visited):** This means $v$ is an ancestor of $u$ on the recursion stack. The edge $(u, v)$ would be a back edge, which implies a cycle. But $G$ is a DAG by assumption, so this case is impossible.
- **$v$ is White (not yet visited):** $v$ becomes a descendant of $u$. DFS will visit $v$ and the entire subtree reachable from it, finishing its visit before the visit of $u$ is finished. Hence $post[v] post[v]$. Since vertices are ordered by decreasing values of `post`, $u$ will always precede $v$, ensuring the correctness of the topological sort.
