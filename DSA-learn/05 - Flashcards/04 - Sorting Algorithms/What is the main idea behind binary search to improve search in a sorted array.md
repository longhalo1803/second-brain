---
title: "What is the main idea behind binary search to improve search in a sorted array"
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
  - "What is the main idea behind binary search to improve search in a sorted array"
---

# 🎴 What is the main idea behind binary search to improve search in a sorted array

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: What is the main idea behind **binary search** to improve search in a sorted array? #card

?
The main idea consists of exploiting the sorting of the array using a halving strategy:

1. Compare $key$ with the element at the _central position_ $k$ of $L$.
2. If they are equal, the element has been found and $k$ is returned.
3. If $key > L[k]$, continue searching in the same way only in the portion to the **RIGHT** of $k$ (from $k+1$).
4. Otherwise (if $key AlwaysAngry - Own work, CC BY-SA 4.0, Link
