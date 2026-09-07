---
title: "What are the two fundamental properties required for the greedy technique to be ap..."
tags:
  - dsa
  - flashcards
  - clrs
  - trees-heaps
type: reference
status: completed
created: 2026-09-25
updated: 2026-09-25
aliases:
  - "What are the two fundamental properties required for the greedy technique to be ap..."
---

# 🎴 What are the two fundamental properties required for the greedy technique to be ap...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: What are the two fundamental properties required for the greedy technique to be applicable? #card

?
The greedy technique can be successfully applied (guaranteeing the optimality of the global solution) if the following two properties hold for the **problem **and the **algorithm**:

- **Optimal substructure:** an optimal solution to the problem contains within it the optimal solutions to the related subproblems.
  In other words, this property allows building the optimal solution of a larger problem by relying directly on the optimal solutions already found for smaller problems.
-

📝 Example (shortest paths on graphs):
If a node $v$ lies on the shortest path $P$ from source node $s$ to destination node $u$, then the subpath of $P$ from $s$ to $v$ is itself the shortest path from $s$ to $v$.

- **Greedy choice property:** the greedy choice made at each step allows choosing an element of the solution that is indeed part of a globally optimal solution.
  In other words, it guarantees that a short-sighted local choice (the 'greedy' choice) is always compatible with reaching the global optimum: _you can reach the globally best solution by choosing the locally best option at each stage. You make the choice that looks best at the moment without looking back or modifying past choices_.

- 📝 Example (Dijkstra's algorithm for shortest paths):
  At each iteration, Dijkstra's greedy choice consists of selecting the node present in the priority queue that has the **minimum tentative distance** (highest priority) from the source $s$.
  Since there are no negative weights in the graph, the distance computed for that node at that precise moment is guaranteed to be the definitive shortest distance, allowing the algorithm to "commit" to the choice without ever having to re-examine it later.
