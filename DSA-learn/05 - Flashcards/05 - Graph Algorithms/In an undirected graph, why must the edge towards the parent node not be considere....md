---
title: "In an undirected graph, why must the edge towards the parent node not be considere..."
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
  - "In an undirected graph, why must the edge towards the parent node not be considere..."
---

# 🎴 In an undirected graph, why must the edge towards the parent node not be considere...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Graph Algorithms MOC|📁 Graph Algorithms MOC]]

---

### Q: In an undirected graph, why must the edge towards the parent node not be considered a cycle, and how is it distinguished from a true Back-Edge? #card

?
In an undirected graph, each undirected edge $\{v, u\}$ is examined in both directions: from $v$ to $u$ and subsequently from $u$ to $v$.

**Why the edge to the parent does not indicate a cycle:**
If DFS moves from $u$ to $v$ (setting `prev[v] = u`), when DFS examines the neighbors of $v$, it will also find node $u$ among them. This node $u$ is already visited, but the edge $(v,u)$ is simply the **same undirected edge** traversed in reverse, not a cycle in the graph!
In other words, the check `prev[v] != u` is performed to ensure we do not go back toward the node we just arrived from: in an undirected graph, the edge $(v, u)$ exists in both directions, re-traversing it back to the parent does not constitute a cycle.

**Formal condition to identify a Back-Edge:**
An edge $(v, u)$ is a **true Back-Edge** (and therefore indicates a cycle) if and only if:

```text
visited[u] = TRUE AND prev[v] ≠q u
```

that is, $u$ is already visited and **is not the immediate parent** of $v$.
