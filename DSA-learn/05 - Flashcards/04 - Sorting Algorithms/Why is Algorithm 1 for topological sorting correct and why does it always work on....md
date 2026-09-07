---
title: "Why is Algorithm 1 for topological sorting correct and why does it always work on..."
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
  - "Why is Algorithm 1 for topological sorting correct and why does it always work on..."
---

# 🎴 Why is Algorithm 1 for topological sorting correct and why does it always work on...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: Why is Algorithm 1 for topological sorting correct and why does it always work on a DAG? #card

?
Algorithm 1 is correct for the following reasons:

- **Existence of a source:** every finite DAG always has at least one source vertex ($\text{in-degree} = 0$). Since a source vertex has no incoming edges, it has no unmet dependencies and can be placed at the beginning of the ordering.
- **Preservation of the DAG property:** removing a vertex and its outgoing edges leaves a subgraph that is still a DAG (of smaller size), ensuring the presence of a new source in the next step.
- **Correctness for generic and sink vertices:** a vertex $v$ is selected only when its $\text{in-degree}$ becomes 0, i.e., when all vertices that had an edge pointing to $v$ have already been processed and placed to the left of $v$. Sink vertices ($\text{out-degree} = 0$) are taken last.
