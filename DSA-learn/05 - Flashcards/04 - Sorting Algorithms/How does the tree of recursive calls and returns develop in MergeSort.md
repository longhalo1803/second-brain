---
title: "How does the tree of recursive calls and returns develop in MergeSort"
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
  - "How does the tree of recursive calls and returns develop in MergeSort"
---

# 🎴 How does the tree of recursive calls and returns develop in MergeSort

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: How does the tree of recursive calls and returns develop in MergeSort?

📝 Show it, for example, for the array [33, 21, 7, 48, 28, 13, 65, 17]. #card
?
The execution of MergeSort follows a **top-down** strategy for the recursive calls and a **bottom-up** strategy for returning results and merging (`Merge`).

📝 **Example with the array:** `[33, 21, 7, 48, 28, 13, 65, 17]`

Static SVG version

📌 **Execution dynamics:**

- The algorithm first descends **completely to the left** down to the base cases with just 1 element (e.g., `[33]` and `[21]`).
- It performs the first `Merge`, which returns the sorted pair `[21, 33]`.
- It proceeds similarly on the right sub-tree of the left side (producing `[7, 48]`), then merges the two blocks to obtain `[7, 21, 33, 48]`.
- It repeats the entire process for the right half of the initial array prior to the final large `Merge`.
