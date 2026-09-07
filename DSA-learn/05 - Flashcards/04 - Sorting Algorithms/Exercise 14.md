---
title: "Exercise 14"
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
  - "Exercise 14"
---

# 🎴 Exercise 14

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: 📝 Exercise 14

An undirected graph $G = (V, E)$ is called bipartite if its vertices can be partitioned into two subsets $V_1$ and $V_2$ (that is, such that $V_1 \cap V_2 = \emptyset$ and $V_1 \cup V_2 = V$) such that no edges exist between vertices of the same subset (that is, if $(u, v) \in E$ then $u \in V_1$ and $v \in V_2$ or vice versa).

• Prove that a graph is bipartite if and only if it contains no odd-length cycles (where the length of a cycle is the number of edges in the cycle).
• Describe an algorithm to check whether the graph is bipartite. If it is, the algorithm must return the partition $V_1, V_2$; if not, it must return an odd-length cycle.
• Discuss the running time of the proposed algorithm. #card
?
We prove both directions (first "if" and then "only if"):

**IF $\Rightarrow$:
**If the graph is bipartite, there are no edges between nodes of $V_1$ nor between nodes of $V_2$.
Any path in the graph will necessarily alternate between a node in $V_1$ and a node in $V_2$.
A path that begins and ends at the same node (a cycle) must therefore contain an even number of edges.
It is impossible to have odd-length cycles.

**ONLY IF $\Leftarrow$:
**Assume for contradiction that an odd cycle exists and the graph is bipartite.
Consider a node of the cycle in $V_1$: its neighbors must be in $V_2$.
Continuing along the cycle alternating sets, because the length is odd, the node immediately preceding the starting node would have to belong to $V_1$, creating an edge between two nodes both in $V_1$, which is a contradiction.

---

**Algorithm:**
Use an array of $n$ elements $P$ that records which partition each node belongs to ($P[v] = 0$ if $v \in V_1$, $P[v] = 1$ if $v \in V_2$). Run a depth-first search (DFS) or breadth-first search (BFS) using a $\textsf{VISITED}$ array.
Each time an edge $(u, v)$ is analyzed:
• If $\textsf{VISITED}[v] = \textsf{FALSE}$, node v must go into the other partition relative to node u (we can set $P[v] := (P[u] + 1) \bmod 2$).
• If $\textsf{VISITED}[v] = \textsf{TRUE}$ and $P[u] \neq P[v]$, continue.
• If $P[u] = P[v]$, stop the search and return the odd-length cycle.
If the traversal finishes without conflicts, return the partition $P$.

**3. Running time:** the same as DFS/BFS: $O(|V| + |E|)$.
