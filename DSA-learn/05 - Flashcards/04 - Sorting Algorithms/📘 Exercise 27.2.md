---
title: "📘 Exercise 27.2"
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
  - "📘 Exercise 27.2"
---

# 🎴 📘 Exercise 27.2

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: 📘 Exercise 27.2

**Input:** A connected DAG $G = (V, E)$ with $V = \{1, \dots, n\}$.
**Output:** TRUE if there exists a directed path that passes through all nodes of the graph (Hamiltonian path), FALSE otherwise.

- Show two examples with at least 5 nodes and 6 edges (one TRUE, one FALSE).
- Describe an algorithm in words and provide pseudocode in $O(|V| + |E|)$ time.
- Argue correctness and computational complexity.
- **Extra:** Would the algorithm work if the path had to pass through $|V| - 1$ nodes? Justify. #card
  ?
  **Reasoning:**
  In a DAG, a Hamiltonian path exists if and only if the topological sort of the graph is unique. Equivalently, if $v_1, v_2, \dots, v_n$ is the topological order, there must be a directed edge $(v_i, v_{i+1}) \in E$ for every $i \in \{1, \dots, n - 1\}$.

**1. Examples:**
Topological order $[1, 2, 3, 4, 5]$.

- TRUE: Edges $(1, 2), (2, 3), (3, 4), (4, 5), (1, 3), (2, 5)$. Path $1 \to 2 \to 3 \to 4 \to 5$ visits all nodes.
- FALSE: Same edges but remove $(2, 3)$ and add $(1, 4)$. No edge between 2 and 3, so output is FALSE.
  **2. Pseudocode:**

```text
Algorithm HasHamiltonianPath(G, n):
    L ≤ftarrow TopologicalSort(G)
    for i ≤ftarrow 0 to n - 2 do
        u ≤ftarrow L[i], \; v ≤ftarrow L[i+1]
        if not HasEdge(G, u, v) then return FALSE
    return TRUE
```

**3. Correctness & Complexity:**
Any valid path visiting all nodes must follow the topological order. Topological sort takes $O(|V| + |E|)$. Checking the $n - 1$ edges takes $O(|V| + |E|)$. Total time is $O(|V| + |E|)$.

**4. Extra ($|V| - 1$ nodes):**
No. A path skipping one arbitrary node corresponds to finding a Hamiltonian path in a subgraph induced by $|V| - 1$ nodes, which does not require consecutive topological adjacencies across all steps and cannot be determined by merely verifying adjacent elements of a single topological sort.
