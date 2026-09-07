---
title: "How is the Shortest Paths on a DAG (Directed Acyclic Graph) problem formulated Inp..."
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
  - "How is the Shortest Paths on a DAG (Directed Acyclic Graph) problem formulated Inp..."
---

# 🎴 How is the Shortest Paths on a DAG (Directed Acyclic Graph) problem formulated Inp...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Graph Algorithms MOC|📁 Graph Algorithms MOC]]

---

### Q: How is the **Shortest Paths on a DAG** (Directed Acyclic Graph) problem formulated? Input and output? #card

?
**Input:**

- A DAG $G = (V, E)$
- A source node $s \in V$
- An edge cost function $c: E \to \mathbb{R}$**Output:**
  Shortest distances of the nodes of $G$ from the source $s$.

Node D is reachable only from nodes C and B:

$$

\text{dist}[D] = \min \begin{cases} \text{dist}[C] + 3 \\ \text{dist}[B] + 1 \end{cases}

$$

If the distances of C and B from the source are calculated first, the distance of D from the source can be calculated easily.
