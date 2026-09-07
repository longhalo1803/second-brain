---
title: "What is an induced subgraph How does it differ from a generic subgraph"
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
  - "What is an induced subgraph How does it differ from a generic subgraph"
---

# 🎴 What is an induced subgraph How does it differ from a generic subgraph

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Graph Algorithms MOC|📁 Graph Algorithms MOC]]

---

### Q: What is an induced subgraph? How does it differ from a generic subgraph? #card

?
A graph $G'=(V',E')$ is an **induced subgraph** by a subset of vertices $V' \subseteq V$ if $E' \subseteq E$ contains **all** the edges of $E$ that connect nodes belonging to $V'$.

⚠️ Warning:
In a generic subgraph, it is possible to omit edges present in the original graph between the chosen nodes. In an **induced subgraph**, however, if two nodes in $V'$ were connected in $G$, the edge _must necessarily_ also be present in $E'$.

    .graph-toggle-input { display: none; }
    .graph-toggle-label {
      display: inline-block;
      padding: 8px 16px;
      margin: 0 4px 16px 4px;
      cursor: pointer;
      border: 2px solid currentColor;
      border-radius: 6px;
      font-family: sans-serif;
      font-size: 15px;
      font-weight: bold;
      opacity: 0.5;
      user-select: none;
    }
    #toggle-indotto:checked ~ .btn-container label[for="toggle-indotto"],
    #toggle-non-indotto:checked ~ .btn-container label[for="toggle-non-indotto"] {
      opacity: 1;
      background: rgba(128, 128, 128, 0.2);
    }
    .graph-view { display: none; }
    #toggle-indotto:checked ~ #view-indotto { display: block; }
    #toggle-non-indotto:checked ~ #view-non-indotto { display: block; }






    Induced Subgraph
    NON-Induced Subgraph
