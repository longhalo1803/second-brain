---
title: "What is the main idea behind SelectionSort for sorting an array (no pseudocode)"
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
  - "What is the main idea behind SelectionSort for sorting an array (no pseudocode)"
---

# 🎴 What is the main idea behind SelectionSort for sorting an array (no pseudocode)

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: What is the main idea behind SelectionSort for sorting an array? (no pseudocode) #card

?

- Find the **minimum** element among the $n$ elements of the array and swap it with the element at the first position.
- Sort the remaining $n-1$ elements in the same way.
- If there is only one element left to sort ($i = n-1$), the algorithm terminates.📌 Note:
  It is a **recursive** strategy. It reduces the problem of sorting $n$ elements to sorting an identical subproblem of size $n-1$.

By Suaudeau - Own work, CC BY-SA 4.0, Link
