---
title: "Exercise 9"
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
  - "Exercise 9"
---

# 🎴 Exercise 9

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: 📝 **Exercise 9**

A sequence $A[0]A[1]...A[n-1]$ of $n$ DISTINCT elements is said to be **unimodal** if there exists an index $i$, with $0\le i\le n-1$, such that $A[0]A[i+1]>A[i+2]>...>A[n-1]$ (if $i=0$ or $i=n-1$ the sequence is sorted).
Write a recursive function that, in $O(\log n)$ time, finds the maximum of a unimodal sequence given as input.

💡 **Hint**Consider the element in the center of the sequence and determine if the maximum is to the left or right of the central one (warning: the central one could be the maximum). Whenever an $O(\log n)$ cost on sequences is requested, it is a good idea to adapt binary search. #card
?
Let us reason about a subsequence $L[i..j]$ of the array, to determine what the base cases are and which is the non-base case.

- If the sequence contains only one element ($i=j$), this must necessarily be the one sought and is returned → **Base case**.
- If the sequence contains more than one element, we reason as in binary search: having determined the central element at position $k$, three cases may occur:

1. the sought element is to the left of the central one, so $L[k-1]>L[k]>L[k+1]$;
2. the sought element is to the right of the central one, so $L[k-1]L[k+1]$.

In all three cases we need to be able to test a predecessor and a successor of $k$, so we add a base case for when the sequence has exactly two elements:

- If the sequence contains exactly two elements ($i+1=j$), the larger of the two is the element sought → **Base case**.
- Otherwise, if there are at least three elements in $A[i..j]$ ($j>i+1$), the central element $k$ has both a predecessor and a successor in $A[i..j]$; we can therefore test the previous conditions and determine how to proceed:
- if $L[k-1]>L[k]>L[k+1]$, we search for the solution recursively to the left of $k$ (excluded);
- if $L[k-1]L[k+1]$, we return $L[k]$ → **Base case**.

```text
Unimodal(L, i, j)
    if i = j then return L[i]            // only one element in the sequence
    if i + 1 = j then                    // two elements in the sequence
        if L[i] > L[j] then return L[i]
        else return L[j]
    k := floor((i + j) / 2)
    if L[k-1]  L[k+1] then return L[k]    // the central element is the one we are looking for
        else return Unimodal(L, k+1, j)      // recursion on the right part
    else return Unimodal(L, i, k-1)      // recursion on the left part
```

Main call: $\textsf{Unimodal(L, 0, n-1)}$.

**Correctness and termination:** the recursive calls are always invoked on subsequences of size $\ge 1$ (if they were invoked on empty subsequences it would be a problem, because that is not one of the base cases).
If the function is invoked on a subsequence with $n\ge7$ elements, the recursion occurs on a sequence with at least 3 elements (which is not a base case and recursion continues).
If it is invoked with $n=6$ elements, the recursion occurs on a sequence of 3 elements (non-base case) or 2 (base case, handled appropriately).
If it is invoked with $n=5$ elements, the recursion occurs on a sequence of 2 elements (base case).
If it is invoked with $n=4$ elements, the recursion occurs on a sequence of 1 or 2 elements (both base cases).
Finally, if it is invoked with $n=3$ elements, the recursion occurs on a sequence of 1 element (base case).

**Remark:** the reasoning above serves to determine the base cases and the non-base case; in the assignment, however, what is required is the conclusion of this reasoning, i.e., a description of the algorithm such as:
_Base cases_:

1. $n=1$: the only element present is returned.
2. $n=2$: the larger of the two elements is returned.
3. $n\ge3$ and $L[k-1]L[k+1]$, with $k=\lfloor(i+j)/2\rfloor$: $L[k]$ is returned.
   _Non-base case_: $n>2$, with the explanation of how to continue recursion to the left or right of $k$, depending on the comparison between $L[k-1]$, $L[k]$, and $L[k+1]$.
