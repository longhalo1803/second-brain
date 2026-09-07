---
title: "7 Given two lists L and M storing natural numbers sorted in non-decreasing order,..."
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
  - "7 Given two lists L and M storing natural numbers sorted in non-decreasing order,..."
---

# 🎴 7 Given two lists L and M storing natural numbers sorted in non-decreasing order,...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: 📝 7 Given two lists $L$ and $M$ storing natural numbers sorted in non-decreasing order, write a function $\textsf{ListMerge}(L, M)$ (analogous to `Merge` in `MergeSort`) that returns a new list containing all elements of $L$ and $M$ sorted in non-decreasing order. #card

?
Like the merge function of mergesort, there are different ways to solve this problem. The following is just one possibility.

The algorithm works in two steps:

1. **Extraction and insertion:** compare the values at the head of $L$ and $M$. The node with the smaller value is extracted from its list and inserted at the head of a temporary list $R$. The loop terminates when one of the two lists becomes empty.
2. **Reversal and concatenation:** list $R$ contains the elements sorted in reverse order (maximum at the head and minimum at the bottom). List $R$ is reversed by moving its nodes into a new list $T$. Finally, the remaining elements of the non-empty list between $L$ and $M$ are concatenated to the tail of $T$.

**Pseudocode:**

```text
{aligned}                            // ListMerge(L, M)
    // R := new_list()
    // while L ≠q NIL AND M ≠q NIL do
        // if L.val ≤ M.val then
            // tmp := L
            // L := L.next
        // else
            // tmp := M
            // M := M.next
        // insert_head(R, tmp)
    // if R = NIL then
        // if L ≠q NIL then return L
        // else return M
    // last := R
    // T := new_list()
    // tmp := R
    // while tmp ≠q NIL do
        // p := tmp.next
        // insert_head(T, tmp)
        // tmp := p
    // if L ≠q NIL then last.next := L
    // else last.next := M
    // return T
```

📌 Note: the computational cost is $\Theta(n + m)$, where $n$ and $m$ are the lengths of lists $L$ and $M$.
