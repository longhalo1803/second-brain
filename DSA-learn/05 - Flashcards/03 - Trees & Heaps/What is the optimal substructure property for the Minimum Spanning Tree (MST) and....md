---
title: "What is the optimal substructure property for the Minimum Spanning Tree (MST) and..."
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
  - "What is the optimal substructure property for the Minimum Spanning Tree (MST) and..."
---

# 🎴 What is the optimal substructure property for the Minimum Spanning Tree (MST) and...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: What is the **optimal substructure property** for the Minimum Spanning Tree (MST) and how is it proved? #card

?
Given an MST $T = (V, E')$ for a graph $G = (V, E)$, if any edge $(u,v) \in E'$ is removed, the tree is split into two isolated subtrees $T_1$ and $T_2$.
These subtrees are themselves **MSTs for their respective sets of connected vertices**.

**Proof (via Cut-and-Paste technique / by contradiction):**
Let $T = T_1 \cup T_2 \cup \{(u,v)\}$ with cost $\text{cost}(T) = \text{cost}(T_1) + \text{cost}(T_2) + c(u,v)$.

- Assume for the sake of contradiction that $T_1$ is **not** an MST for the set of vertices it spans.
- Then there must exist an alternative spanning tree $T_1'$ for the same vertices with strictly lower cost: $\text{cost}(T_1') < \text{cost}(T_1)$.
- We construct a new spanning tree for the entire graph $G$:

$$

T' = T_1' \cup T_2 \cup \{(u,v)\}

$$

- The cost of the new tree will be:

$$

\text{cost}(T') = \text{cost}(T_1') + \text{cost}(T_2) + c(u,v) < \text{cost}(T)

$$

- This contradicts the initial assumption that $T$ is an MST for $G$.Therefore, both $T_1$ and $T_2$ must necessarily be MSTs for their respective subsets of nodes. $\blacksquare$
