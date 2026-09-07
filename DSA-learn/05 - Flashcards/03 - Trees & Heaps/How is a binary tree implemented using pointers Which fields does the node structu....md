---
title: "How is a binary tree implemented using pointers Which fields does the node structu..."
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
  - "How is a binary tree implemented using pointers Which fields does the node structu..."
---

# 🎴 How is a binary tree implemented using pointers Which fields does the node structu...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: How is a binary tree implemented **using pointers**? Which fields does the node structure contain? #card

?
A binary tree is represented by dynamically allocating nodes in memory via pointers.

**Standard 3-field node:**
**`left`**: pointer to the left child (`NIL` if absent).
**`right`**: pointer to the right child (`NIL` if absent).
**`val`**: optional value/key stored in the node.

**4-field node (with parent pointer):**
**`left`**: pointer to the left child.
**`right`**: pointer to the right child.
**`parent`**: pointer to the parent node (`NIL` for the root).
**`val`**: value associated with the node.

📌 Note: the tree $T$ is simply represented by the pointer to its **root**.
