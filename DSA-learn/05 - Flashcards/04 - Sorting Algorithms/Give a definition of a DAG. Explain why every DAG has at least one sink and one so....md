---
title: "Give a definition of a DAG. Explain why every DAG has at least one sink and one so..."
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
  - "Give a definition of a DAG. Explain why every DAG has at least one sink and one so..."
---

# 🎴 Give a definition of a DAG. Explain why every DAG has at least one sink and one so...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: ❓ Give a definition of a DAG. Explain why every DAG has at least one sink and one source. Explain what is meant by linearization (or topological sort) of a DAG and explain why it is always possible to linearize a DAG. #card

?

- **Definition of a DAG:**
  A DAG (_Directed Acyclic Graph_) is a directed graph without directed cycles (there is no non-trivial path that starts at a vertex $v$ and returns to $v$).
- **Existence of at least one source and one sink (in a finite DAG):**
- A **source** is a node with zero in-degree; a **sink** is a node with zero out-degree.
- _Proof for the sink:_ Choose an arbitrary vertex $v_1$. If $v_1$ has no outgoing edges, it is a sink. Otherwise, follow an outgoing edge to $v_2$. Repeat the process: from $v_i$, if it has outgoing edges, move to $v_{i+1}$. Since the number of vertices $|V|$ is finite, if the process did not terminate it would eventually have to revisit an already encountered node, which would imply the existence of a directed cycle. Because the graph is acyclic, the path cannot intersect itself and must necessarily terminate after at most $|V|$ steps at a node with no outgoing edges (a sink).
- _Proof for the source:_ Exactly the same reasoning applies backwards by following incoming edges.
- **Linearization (Topological Sort):**
  A topological sort of a DAG $G=(V,E)$ is a linear ordering of all its vertices $v_1, v_2, \dots, v_n$ such that for every directed edge $(u, v) \in E$, vertex $u$ appears before $v$ in the ordering.
- **Why it is always possible to linearize a DAG:**
  We can prove this by induction on the number of nodes $n = |V|$:
- For $n=1$, the ordering is trivial.
- For $n > 1$, we proved that there is always at least one source $s$. Place $s$ as the first element of the linear sequence.
- Remove $s$ and all its outgoing edges from the graph. The induced subgraph $G' = G \setminus \{s\}$ is still a DAG (removing nodes and edges cannot introduce cycles).
- By the inductive hypothesis, $G'$ admits a topological sort. Appending this sort after $s$ yields a valid topological sort for the entire graph $G$, since all edges leaving $s$ go to nodes placed after it and there are no edges entering $s$.
