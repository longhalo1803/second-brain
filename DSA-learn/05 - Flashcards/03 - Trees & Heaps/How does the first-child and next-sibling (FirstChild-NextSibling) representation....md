---
title: "How does the first-child and next-sibling (FirstChild-NextSibling) representation..."
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
  - "How does the first-child and next-sibling (FirstChild-NextSibling) representation..."
---

# 🎴 How does the first-child and next-sibling (FirstChild-NextSibling) representation...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: How does the _**first-child and next-sibling**_ (FirstChild-NextSibling) representation work for general trees? #card

?
It represents any general tree using **exactly two pointers per node**, regardless of the number of children each node has.

**Fields of the node structure (`tree_node`):**

- `firstchild`: pointer to the first child of the node (the leftmost one).
- `nextsibling`: pointer to the immediate next sibling to the right.
- `parent`: (optional) pointer to the parent node.
- `val`: value stored in the node.
  **Advantages:**

- **Zero wasted memory:** the amount of memory is always proportional to $\Theta(n)$.
- Supports an arbitrary number of children without modifying the node data structure.
