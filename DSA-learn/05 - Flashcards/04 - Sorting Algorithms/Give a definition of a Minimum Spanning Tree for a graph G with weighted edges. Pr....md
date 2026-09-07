---
title: "Give a definition of a Minimum Spanning Tree for a graph G with weighted edges. Pr..."
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
  - "Give a definition of a Minimum Spanning Tree for a graph G with weighted edges. Pr..."
---

# 🎴 Give a definition of a Minimum Spanning Tree for a graph G with weighted edges. Pr...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: ❓ Give a definition of a Minimum Spanning Tree for a graph $G$ with weighted edges. Present one of the algorithms for Minimum Spanning Trees on undirected graphs seen previously and argue why it is correct (the underlying idea of the proof). #card

?

- **Definition of MST:**
  Given an undirected, connected graph $G=(V,E)$ with real weights on edges $w: E \to \mathbb{R}$, a Minimum Spanning Tree (MST) is an acyclic subgraph $T = (V, E_T)$ with $E_T \subseteq E$ that connects all vertices in $V$ (hence it is a spanning tree, with $|E_T| = |V|-1$) and minimizes total weight:

$$

w(T) = \sum\_{e \in E_T} w(e)

$$

- **Prim's Algorithm:**
- Start from an arbitrary source vertex $s$, setting a set of already covered nodes $S = \{s\}$ and a set of tree edges $T = \emptyset$.
- At each step, consider the set of edges crossing the cut $(S, V \setminus S)$ (i.e., with one endpoint in $S$ and one outside).
- Select the minimum-weight edge $e = (u, v)$ with $u \in S$ and $v \in V \setminus S$.
- Add $v$ to $S$ and edge $(u, v)$ to $T$.
- Repeat the process until $S = V$.
- **Idea of the Correctness Proof (Cut Property):**
  The proof is based on the **Cut Property**: for any partition of the vertices into two disjoint sets $(S, V \setminus S)$, the light edge (minimum-weight edge) connecting a node in $S$ to a node in $V \setminus S$ necessarily belongs to some minimum spanning tree.
  _Cut-and-Paste Argument:_ Suppose for contradiction that an MST $T^_$ does not contain the light edge $e=(u, v)$ of the cut. Since $T^_$ is connected, there must exist another path between $u$ and $v$ in $T^_$, which must cross the cut via a different edge $e'$. If we remove $e'$ from $T^_$ and insert $e$, we obtain a new spanning tree $T' = (T^* \setminus \{e'\}) \cup \{e\}$. The weight of the new tree is $w(T') = w(T^_) - w(e') + w(e)$. Since $e$ is the light edge of the cut, $w(e) \le w(e')$, hence $w(T') \le w(T^_)$. Thus $T'$ is also an MST containing $e$. Prim's algorithm only adds light edges that respect the cut between the current tree and the remaining nodes, ensuring global optimality.
