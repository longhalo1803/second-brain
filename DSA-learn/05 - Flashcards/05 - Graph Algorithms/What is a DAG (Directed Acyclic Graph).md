---
title: "What is a DAG (Directed Acyclic Graph)"
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
  - "What is a DAG (Directed Acyclic Graph)"
---

# 🎴 What is a DAG (Directed Acyclic Graph)

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Graph Algorithms MOC|📁 Graph Algorithms MOC]]

---

### Q: What is a DAG (Directed Acyclic Graph)? #card

?
It is a **Directed Acyclic Graph**, meaning a directed graph that contains no directed cycles.

**Fundamental properties:**

- Its edges have a direction.
- There is no directed path that starts at a node and returns to the same node.
- It represents asymmetric and non-circular precedence or dependency relationships.
  📝 Example:
  A graph with edges $1 \to 2$, $1 \to 3$, $2 \to 4$, $3 \to 4$ is a DAG.
  If we were to add an edge $4 \to 1$, the cycle $1 \to 2 \to 4 \to 1$ would be formed and it would no longer be a DAG.

📌 Note: in DAGs it is always possible to find a topological ordering.
