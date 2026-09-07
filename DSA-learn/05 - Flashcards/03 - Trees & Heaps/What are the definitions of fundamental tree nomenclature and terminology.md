---
title: "What are the definitions of fundamental tree nomenclature and terminology"
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
  - "What are the definitions of fundamental tree nomenclature and terminology"
---

# 🎴 What are the definitions of fundamental tree nomenclature and terminology

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: What are the definitions of fundamental tree nomenclature and terminology? #card

?
Given a rooted tree structure, relationships between nodes are defined as follows:

- **Root:** the unique node with no incoming edges.
- **Parent (or father):** $father(x)$ denotes the direct parent of node $x$ (e.g., if $A \to B$, then $father(B) = A$).
- **Children:** $children(x)$ is the set of nodes directly connected downward from node $x$ (e.g., $children(F) = \{L, M\}$).
- **Siblings:** $sibling(x)$ is the set of nodes sharing the same parent as $x$ (e.g., $sibling(D) = \{E\}$).
- **Ancestor and Descendant:** a node $u$ is an ancestor of $v$ (and $v$ is a descendant of $u$) if a path exists from $u$ to $v$.
- **Leaves:** nodes that have no children, i.e., $children(x) = \emptyset$.
- **Internal nodes:** nodes that have at least one child.

- A is the **root**

- A is the **parent** (father) of B and C

- B and C are **children** of A

- B and C are **siblings**

- B is an **ancestor** of H

- H is a **descendant** of B

- B is the root of the left **subtree**

- H, I, E, L, M, N, and O are **leaves**; they have no children.

- A, B, D, C, F, and G are **internal nodes**; they have at least one child.
