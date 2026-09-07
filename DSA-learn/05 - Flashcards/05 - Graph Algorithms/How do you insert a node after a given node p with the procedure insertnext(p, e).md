---
title: "How do you insert a node after a given node p with the procedure insertnext(p, e)"
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
  - "How do you insert a node after a given node p with the procedure insertnext(p, e)"
---

# 🎴 How do you insert a node after a given node p with the procedure insertnext(p, e)

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Graph Algorithms MOC|📁 Graph Algorithms MOC]]

---

### Q: How do you insert a node after a given node p with the procedure `insert_next(p, e)`? #card

?
The procedure `insert_next(p, e)` inserts node `e` immediately after the node pointed to by `p`.

**Pseudocode:**

```text
insert_next(p, e)
    e.next := p.next
    p.next := e
```

**Steps:
**1. `e.next` is set to point to the node that currently follows `p`. 2. `p.next` is updated to point to the new node `e`.

**Computational cost:** $\Theta(1)$

⚠️ Warning: the order of the two assignments is fundamental! If `p.next := e` were executed first, the reference to the remainder of the list would be lost.
📌 Note: unlike other primitives, the pointer to the head of the list $\textsf L$ is not passed; having $\textsf p$ is sufficient to insert a new node immediately after it in the linked list.
