---
title: "Present the single-source shortest paths problem with possibly negative edge weigh..."
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
  - "Present the single-source shortest paths problem with possibly negative edge weigh..."
---

# 🎴 Present the single-source shortest paths problem with possibly negative edge weigh...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Graph Algorithms MOC|📁 Graph Algorithms MOC]]

---

### Q: ❓ Present the single-source shortest paths problem with possibly negative edge weights. Present the Bellman-Ford algorithm for solving the problem (pseudocode is not strictly required, pseudocode alone without explanations is not sufficient) and discuss its computational cost. #card

?

- **Single-Source Shortest Paths (SSSP) Problem:**
  Given a weighted directed graph $G = (V, E, w)$ with weight function $w: E \to \mathbb{R}$ and a source vertex $s \in V$, the problem consists of determining the shortest distance $d(s, v)$ from $s$ to every $v \in V$. If the graph contains negative-weight edges, **negative cycles** reachable from $s$ may appear: in that case, the shortest path is not well-defined for vertices reachable from the cycle (the cost diverges to $-\infty$). The algorithm must either compute the correct distances or detect the presence of negative-weight cycles.
- **Bellman-Ford Algorithm:**
- **Initialization:** For each $v \in V$, set an estimated distance $d[v] = \infty$ and predecessor $\pi[v] = \text{NIL}$; for the source, set $d[s] = 0$.
- **Relaxations:** The algorithm performs $|V| - 1$ iterations. In each iteration, it examines **all** edges $(u, v) \in E$ and performs the relaxation step (_relax_):

```text
if d[u] + w(u, v) < d[v] d[v] = d[u] + w(u, v), [v] = u
```

_Explanation:_ Since every simple shortest path contains at most $|V| - 1$ edges, after $i$ iterations all shortest path distances consisting of at most $i$ edges have been computed correctly.

- **Negative cycle detection:** Iterate one additional time over all edges $(u, v) \in E$. If there exists an edge for which $d[u] + w(u, v) < d[v]$ still holds, it means that the distance can be reduced further, which can only happen if a reachable negative cycle exists. In this case, the algorithm signals the presence of the cycle and returns `FALSE`. Otherwise, it returns `TRUE` along with the correct minimum distances.
- **Computational Cost:**
- Initialization: $\mathcal{O}(|V|)$.
- Relaxations: $|V| - 1$ passes over all edges $E$, hence $(|V|-1) \cdot |E| = \mathcal{O}(|V| \cdot |E|)$.
- Negative cycle check: an additional pass over $E$, hence $\mathcal{O}(|E|)$. The total time is therefore $\mathcal{O}(|V| \cdot |E|)$. Auxiliary space is $\mathcal{O}(|V|)$ to maintain the distance and predecessor arrays.
