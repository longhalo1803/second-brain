---
title: "Exercise 6"
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
  - "Exercise 6"
---

# 🎴 Exercise 6

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: 📝📍 Exercise 6

Suppose we use the implementation of `MergeSort` that sorts subsequences of size $\le l$ using `InsertionSort`. In each of the following cases, given the length of sequence $A$ to be sorted, indicate the number of recursive calls that the algorithm performs to sort $A$:

1. $|A|=62$ and $l=6$;
2. $|A|=38$ and $l=4$;
3. $|A|=41$ and $l=4$;
4. $|A|=38$ and $l=6$.

_Warning:_ MergeSort is NOT invoked for subsequences that have size $\le l$. #card
?
Recursive call tree for MergeSort with threshold $\ell$.

**📌 Calculation note:** each node in the tree represents a call with the input size. Only recursive calls to MergeSort are counted.
When the size of the subsequence becomes $\le \ell$, the algorithm makes no further recursive calls but invokes InsertionSort instead; therefore lower levels with size $\le \ell$ (indicated by X in the figure) are not counted in the MergeSort total. Thus:

- **$|A|=62$ and $l=6$:** The number of recursive calls to MergeSort is **15**.
  _Detail:_ 1 (size 62) + 2 (size 31) + 4 (sizes 15,16) + 8 (sizes 7,8) = 15 calls. For sizes $\le 6$, InsertionSort is invoked.
- **$|A|=38$ and $l=4$:** The number of recursive calls is **13**.
- **$|A|=41$ and $l=4$:** The number of recursive calls is **15**.
- **$|A|=38$ and $l=6$:** The number of recursive calls is **7**.
