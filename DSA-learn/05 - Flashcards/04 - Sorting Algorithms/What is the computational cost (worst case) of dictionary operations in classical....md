---
title: "What is the computational cost (worst case) of dictionary operations in classical..."
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
  - "What is the computational cost (worst case) of dictionary operations in classical..."
---

# 🎴 What is the computational cost (worst case) of dictionary operations in classical...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: What is the computational cost (worst case) of dictionary operations in **classical implementations** compared to the ideal case? #card

?
The time complexity comparison (for $n$ stored elements) is:

Structure`insert``lookup``remove`**Unsorted Array**$O(1)$$O(n)$$O(n)$**Sorted Array**$O(n)$$O(\log n)$$O(n)$**Unsorted List**$O(1)$$O(n)$$O(n)$**Sorted List**$O(n)$$O(n)$$O(n)$**BST (Binary Search Tree)**$O(n)$$O(n)$$O(n)$Ideal Case$O(1)$$O(1)$$O(1)$
📌 Note: the concrete **alternative** to approach the performance of the ideal case in average time is the **Hash Table**.
