---
title: "What are the main differences between Dijkstra's algorithm and the Bellman-Ford al..."
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
  - "What are the main differences between Dijkstra's algorithm and the Bellman-Ford al..."
---

# 🎴 What are the main differences between Dijkstra's algorithm and the Bellman-Ford al...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Graph Algorithms MOC|📁 Graph Algorithms MOC]]

---

### Q: What are the main differences between Dijkstra's algorithm and the Bellman-Ford algorithm for the SSSP problem? #card

?
FeatureDijkstraBellman-Ford**Negative weights**❌ Not allowed✅ Allowed (provided no negative cycles)**Negative cycle detection**❌ No✅ Yes (via an extra pass)**Approach**Greedy (selects node with min dist)Dynamic programming / Global relaxation**Time complexity**$O((|V| + |E|) \log |V|)$$O(|V| \cdot |E|)$
