---
title: "What is a topological ordering (or linearization) of a DAG"
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
  - "What is a topological ordering (or linearization) of a DAG"
---

# 🎴 What is a topological ordering (or linearization) of a DAG

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Graph Algorithms MOC|📁 Graph Algorithms MOC]]

---

### Q: What is a topological ordering (or linearization) of a DAG? #card

?
Given a DAG $G=(V,E)$, a **topological ordering** is a linear ordering of its vertices such that for every directed edge $(u,v) \in E$, vertex $u$ comes before $v$ in the ordering.

**Visual property:** if the vertices are laid out on a line from left to right according to this ordering, all directed edges point **consistently from left to right**.

📌 Note: a DAG may admit more than one valid topological ordering.
📝 Example: for a DAG with vertices $\{1, 2, 3, 4, 5\}$, two possible topological orderings are:
$1, 3, 5, 4, 2$
$3, 4, 5, 1, 2$
