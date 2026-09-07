---
title: "Write the pseudocode for recursive binary search."
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
  - "Write the pseudocode for recursive binary search."
---

# 🎴 Write the pseudocode for recursive binary search.

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: 🟢 Write the pseudocode for ****recursive** binary search**. #card

?

```text
BinarySearch(L, i, j, key)
    if j - i  j due to the return that immediately exits the function.
⚠️ Warning: standard binary search finds an element equal to the target, but if there are duplicates **it does not guarantee returning the index of the first occurrence**. It may return any position among those containing the value.
If you wanted to get the first one, you would need to change the behavior when an equality is found: instead of immediately doing `return k`, save `k` as a possible answer and continue searching in the left half (remember: values are sorted).
```
