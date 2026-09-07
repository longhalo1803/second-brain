---
title: "When is a graph G'=(V',E') called a subgraph of G=(V,E)"
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
  - "When is a graph G'=(V',E') called a subgraph of G=(V,E)"
---

# 🎴 When is a graph G'=(V',E') called a subgraph of G=(V,E)

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Graph Algorithms MOC|📁 Graph Algorithms MOC]]

---

### Q: When is a graph $G'=(V',E')$ called a subgraph of $G=(V,E)$? #card

?
A graph $G'=(V',E')$ is a **subgraph** of $G=(V,E)$ if $G'$ is a valid graph and satisfies the following inclusion conditions:

```text
V' V and E' (V' V') E
```

That is, the vertices of $G'$ are a subset of the vertices of $G$, and the edges of $G'$ are a subset of the edges of $G$ restricted to the vertices $V'$.
