---
title: "How is an optimization problem formally structured and what are its key components"
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
  - "How is an optimization problem formally structured and what are its key components"
---

# 🎴 How is an optimization problem formally structured and what are its key components

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Graph Algorithms MOC|📁 Graph Algorithms MOC]]

---

### Q: How is an optimization problem formally structured and what are its key components? #card

?
An **optimization problem** requires finding a solution that minimizes or maximizes a given objective function among all feasible solutions.

The fundamental components are:

- **INPUT:** the problem's input data.
- **Feasible solution:** a solution that satisfies all constraints imposed by the problem.
- **Cost of the feasible solution:** the value (or set of values) associated with a specific feasible solution.
- **Objective function:** the optimization criterion (finding the _minimum_ or the _maximum_).
- **Optimal solution:** a feasible solution that minimizes (or maximizes) the objective function.
  📝 Example (_Single-source shortest paths_):
  ********\*\*\*\*********InputConnected undirected graph $G=(V,E)$, source node $s$, edge weight functionFeasible solutionSet of $|V|-1$ paths, each being the path from $s$ to every node of the graphSolution costSet of $|V|-1$ values, each equal to the cost of one of the paths in the solutionObjective function**Minimum**Optimal solutionSet of $|V|-1$ paths, each being the minimum-cost path from $s$
