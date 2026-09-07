---
title: "📘 Exercise 26.2"
tags:
  - dsa
  - flashcards
  - clrs
  - sorting
type: reference
status: completed
created: 2026-09-25
updated: 2026-09-25
aliases:
  - "📘 Exercise 26.2"
---

# 🎴 📘 Exercise 26.2

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: 📘 Exercise 26.2

A water network is modeled as a DAG $G = (V, E)$ where each node represents a cistern and each directed edge $(u, v)$ is a channel. Each cistern has a maximum capacity $capacity[v]$ and a local inflow $own\_flow[v]$. Each cistern retains up to its capacity; any excess water is divided equally among all outgoing channels. If a cistern has no outgoing channels, excess water is lost.

**Input:** DAG $G=(V,E)$, arrays $capacity$ and $own\_flow$.
**Output:** The number of cisterns that end up completely full ($water \ge capacity[v]$).

Describe the algorithm, provide pseudocode, and analyze computational complexity. #card
?
**Reasoning:**
Since the network is a DAG, water flows without cycles. We can process cisterns in topological order so that when a cistern is processed, all incoming flows have already been determined.

**Algorithm Description:**
Compute a topological ordering of $G$. Initialize an array $total\_water[v] = own\_flow[v]$. Iterate through vertices in topological order: compare $total\_water[u]$ with $capacity[u]$. If $total\_water[u] > capacity[u]$ and $u$ has out-degree $d_{out}(u) > 0$, calculate excess $(total\_water[u] - capacity[u]) / d_{out}(u)$ and add it to each neighbor $v \in Adj[u]$. Count all nodes where $total\_water[v] \ge capacity[v]$.

**Pseudocode:**

```text
Algorithm CountFullCisterns(G, capacity, own_flow, n):
    L ≤ftarrow TopologicalSort(G)
    water ≤ftarrow copy of own_flow
    for each u ∈ L do
        if water[u] > capacity[u] |Adj[u]| > 0 then
            excess_per_edge ≤ftarrow (water[u] - capacity[u]) / |Adj[u]|
            for each v ∈ Adj[u] do
                water[v] ≤ftarrow water[v] + excess_per_edge
    full_count ≤ftarrow 0
    for i ≤ftarrow 1 to n do
        if water[i] ≥ capacity[i] then
            full_count ≤ftarrow full_count + 1
    return full_count
```

**Complexity:**
Topological sort and flow propagation take $\Theta(|V| + |E|)$ time and $\Theta(|V|)$ auxiliary space.
