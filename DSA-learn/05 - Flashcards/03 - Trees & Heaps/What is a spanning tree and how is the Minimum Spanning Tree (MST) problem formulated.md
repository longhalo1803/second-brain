---
title: "What is a spanning tree and how is the Minimum Spanning Tree (MST) problem formulated"
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
  - "What is a spanning tree and how is the Minimum Spanning Tree (MST) problem formulated"
---

# 🎴 What is a spanning tree and how is the Minimum Spanning Tree (MST) problem formulated

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: What is a spanning tree and how is the Minimum Spanning Tree (MST) problem formulated? #card

?
A **spanning tree** for a connected undirected graph $G = (V, E)$ is a subgraph $T = (V, E')$ such that:

- $E' \subseteq E$;
- $T$ is a **tree**, hence it connects all vertices $V$, contains no cycles, and has exactly $|E'| = |V| - 1$ edges.
  **Minimum Spanning Tree (MST):**

- **Input:** connected undirected graph $G = (V, E)$ and an edge weight function $c : E \to \mathbb{R}$.
- **Feasible solution:** any spanning tree $T = (V, E')$ for $G$.
- **Solution cost:** the sum of the weights of all edges comprising the tree:

$$

\text{cost}(T) = \sum\_{e \in E'} c(e)

$$

- **Objective function:** minimum (minimize the total cost).
- **Output (optimal solution):** a minimum weight spanning tree $T$ (MST).
