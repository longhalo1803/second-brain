---
title: "What is a Binary Max-Heap and how does it differ from a Min-Heap"
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
  - "What is a Binary Max-Heap and how does it differ from a Min-Heap"
---

# 🎴 What is a Binary Max-Heap and how does it differ from a Min-Heap

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: What is a Binary Max-Heap and how does it differ from a Min-Heap? #card

?
Given a totally orderable set of keys, a **Binary Max-Heap** is a binary tree that stores keys from the set and satisfies the following properties:

- **Structure/topology**: identical to the Min-Heap → nearly complete binary tree leaning to the left.
- **Ordering (Max-Heap)**: for each node $v$ of the tree, the key stored in $v$ is ****greater than or equal to**** ($\ge$) the keys stored in the subtree rooted at $v$.
  📌 Note: the root of a Max-Heap always stores the **maximum** value of the entire heap.

⚠️ Warning: ordering in a heap is strictly vertical (along root-to-leaf paths), _not_ horizontal between nodes on the same level or in different branches.

📝 **Max-Heap Example**:
