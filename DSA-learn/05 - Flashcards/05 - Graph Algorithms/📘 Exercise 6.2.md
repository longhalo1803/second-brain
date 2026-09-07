---
title: "📘 Exercise 6.2"
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
  - "📘 Exercise 6.2"
---

# 🎴 📘 Exercise 6.2

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Graph Algorithms MOC|📁 Graph Algorithms MOC]]

---

### Q: 📘 Exercise 6.2

In an undirected graph $G = (V, E)$ with node weights $w: V \to \mathbb{Z}$, a path $\langle v_1, v_2, \dots, v_k \rangle$ is _monotone_ if $w(v_1) < w(v_2) < \dots < w(v_k)$.

**Input:** Graph $G=(V,E)$, weight function $w$, source $s$, destination $d$.
**Output:** Print the nodes on a monotone path from $s$ to $d$ if one exists, or print "no monotone path exists".

- Show an example with at least 7 nodes where a monotone path has length at least 3 edges.
- Describe and provide pseudocode of an algorithm for this problem.
- Analyze the computational complexity.
- **Bonus:** Prove that any monotone path in a node-weighted graph is acyclic. #card
  ?
  **Reasoning:**
  Direct every edge $\{u, v\}$ from lower weight to higher weight: $(u, v)$ exists if $\{u, v\} \in E$ and $w(u) < w(v)$. This transformed graph is a DAG. We then perform a DFS or BFS from $s$ to find a path to $d$.

**1. Example:**
Vertices $1 \dots 7$ with weights $w = [10, 20, 30, 40, 5, 15, 25]$. Edges include $(1, 2), (2, 3), (3, 4)$. Path from 1 to 4 has weights $10 < 20 < 30 < 40$, which is monotone of length 3.

**2. Algorithm Description:**
Run DFS starting at $s$. When visiting $u$, only traverse to neighbor $v$ if $w(u) < w(v)$ and $v$ is unvisited. Keep parent pointers to reconstruct and print the path if $d$ is reached.

**3. Pseudocode:**

```text
Algorithm FindMonotonePath(G, w, s, d):
    visited[] ≤ftarrow array of false; \; parent[] ≤ftarrow array of NIL
    found ≤ftarrow DFS_Monotone(s, d, G, w, visited, parent)
    if not found then print "no monotone path exists"
    else PrintPath(d, parent)

Function DFS_Monotone(u, d, G, w, visited, parent):
    visited[u] ≤ftarrow true
    if u = d then return TRUE
    for each v ∈ Adj[u] do
        if not visited[v] w(u) < w(v) then
            parent[v] ≤ftarrow u
            if DFS_Monotone(v, d, G, w, visited, parent) then return TRUE
    return FALSE
```

**4. Complexity:**
Traverses each vertex and edge at most once: $O(|V| + |E|)$ time and $O(|V|)$ space.

**5. Proof that Monotone Path is Acyclic:**
Suppose for contradiction a monotone path contains a cycle: $\langle u_1, u_2, \dots, u_k, u_1 \rangle$. By definition, $w(u_1) < w(u_2) < \dots < w(u_k) < w(u_1)$. By transitivity of $<$, $w(u_1) < w(u_1)$, which is impossible. Thus, no node can be repeated, and the path is strictly acyclic.
