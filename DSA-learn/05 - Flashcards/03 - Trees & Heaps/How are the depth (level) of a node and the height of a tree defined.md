---
title: "How are the depth (level) of a node and the height of a tree defined"
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
  - "How are the depth (level) of a node and the height of a tree defined"
---

# 🎴 How are the depth (level) of a node and the height of a tree defined

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: How are the depth (level) of a node and the height of a tree defined? #card

?
The dimensions and levels of a tree are defined as follows:

- **Depth or Level of a node:** the length of the simple path (measured in **number of edges**) from the root of the tree to the considered node.
  📌 The root has depth/level equal to $0$.
- **Height of the tree:** the **maximum depth** among all the leaves of the tree.
  📝 Example:
  A node at a distance of 2 edges from the root is at level 2 (depth 2). If the farthest leaf is at level 3, the tree has height $h = 3$.
