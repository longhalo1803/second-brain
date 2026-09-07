---
title: "[review] What is optimal substructure and why is it a fundamental condition for th..."
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
  - "[review] What is optimal substructure and why is it a fundamental condition for th..."
---

# 🎴 [review] What is optimal substructure and why is it a fundamental condition for th...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: [review] What is **optimal substructure** and why is it a fundamental condition for the applicability of Dynamic Programming? #card

?
A problem exhibits **optimal substructure** if optimal solutions to subproblems can be combined to find the optimal solution to the larger problem instance.

**Key properties:**

1. Optimal solutions to subproblems serve as building blocks to construct the global solution.
2. Choices made to solve subproblems optimally **must not be modified** when the subproblem solution becomes part of the larger problem's solution.

📝 Example:
In the shortest paths problem, if a node $v$ lies on a shortest path $P$ from $s$ to $u$, then the subpath of $P$ from $s$ to $v$ is itself a shortest path from $s$ to $v$.
