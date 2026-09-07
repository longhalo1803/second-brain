---
title: "BFS (Breadth-First Search) as it is does not solve the shortest path problem on gr..."
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
  - "BFS (Breadth-First Search) as it is does not solve the shortest path problem on gr..."
---

# 🎴 BFS (Breadth-First Search) as it is does not solve the shortest path problem on gr...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Graph Algorithms MOC|📁 Graph Algorithms MOC]]

---

### Q: BFS (Breadth-First Search) as it is does not solve the shortest path problem on graphs with edge weights. Why? #card

?
BFS is not sufficient because it computes shortest paths considering solely the **number of edges** (unweighted distance) and not their **weight** (or equivalently, it assumes all weights are unit).

**⚠️ **In a weighted graph, a path consisting of _more edges_ may have a lower total weight than a path consisting of _fewer edges_.

📝 Example:
To reach node $4$ from $s$ ($1$), there is a path $1 \to 2 \to 4$ of weight $6$ ($4 + 2$), but there is also a path $1 \to 3 \to 2 \to 4$ of total weight $5$ (three edges of weight $2$, $1$, and $2$).
BFS would visit $4$ via the path $1 \to 2 \to 4$, assigning it a distance of $2$ edges (weight $6$), ignoring the path $1 \to 3 \to 2 \to 4$ which, despite having more edges ($3$), has a smaller total weight ($5$).
