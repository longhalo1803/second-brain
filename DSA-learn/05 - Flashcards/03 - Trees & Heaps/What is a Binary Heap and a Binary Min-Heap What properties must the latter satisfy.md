---
title: "What is a Binary Heap and a Binary Min-Heap What properties must the latter satisfy"
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
  - "What is a Binary Heap and a Binary Min-Heap What properties must the latter satisfy"
---

# 🎴 What is a Binary Heap and a Binary Min-Heap What properties must the latter satisfy

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: What is a Binary Heap and a Binary Min-Heap? What properties must the latter satisfy? #card

?
Given a totally orderable set of keys, a **binary heap** is a binary tree that stores keys from the set (one key per node) and satisfies the following properties:

- **Structure/topology**: the tree is a _nearly complete binary tree leaning to the left_ (it is complete up to the second-to-last level and all leaves at the last level are packed to the left).
- **Ordering (Min-Heap)**: for each node $v$ of the tree, the key stored in $v$ is ****less than or equal to**** ($\le$) the keys stored in the subtree rooted at $v$.
  📌 Note: the root of a Min-Heap always stores the **minimum** key of the entire heap.

📝 **Min-Heap Example**:

Also read: https://algs4.cs.princeton.edu/24pq/ and https://opendsa-server.cs.vt.edu/ODSA/Books/CS3/html/Heaps.html
