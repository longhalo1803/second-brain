---
title: "What are the two fundamental properties required for the greedy technique to be su..."
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
  - "What are the two fundamental properties required for the greedy technique to be su..."
---

# 🎴 What are the two fundamental properties required for the greedy technique to be su...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: What are the two fundamental properties required for the _**greedy**_ technique to be successfully applied to a problem? #card

?
The greedy technique is applicable if the following two properties hold:

1. **Optimal substructure** (property of the _problem_):
   An optimal solution to the problem contains within it optimal solutions to the corresponding subproblems.
   📝 Example: in Dijkstra, if a node $v$ lies on a shortest path $P$ from $s$ to $u$, then the subpath of $P$ from $s$ to $v$ is itself a shortest path to $v$.

2. **Greedy-choice property** (property of the _algorithm_):
   The greedy choice allows making a locally optimal choice at each step that is part of a globally optimal solution.
   📝 Example: in Dijkstra, the greedy choice consists of selecting at each iteration the node in the priority queue having the minimum distance estimate.
