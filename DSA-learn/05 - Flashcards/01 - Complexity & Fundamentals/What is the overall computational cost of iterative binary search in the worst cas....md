---
title: "What is the overall computational cost of iterative binary search in the worst cas..."
tags:
  - dsa
  - flashcards
  - clrs
  - complexity
type: reference
status: completed
created: 2026-09-25
updated: 2026-09-25
aliases:
  - "What is the overall computational cost of iterative binary search in the worst cas..."
---

# 🎴 What is the overall computational cost of iterative binary search in the worst cas...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Complexity & Fundamentals MOC|📁 Complexity & Fundamentals MOC]]

---

### Q: What is the overall **computational cost** of iterative binary search in the worst case compared to the naive solution?

````text
BinarySearch(L, n, key)
    i := 0                               // {#D9534F}{O(1)}
    j := n - 1                           // {#D9534F}{O(1)}
    while i ≤ j do                       // {#2A7AE2}{?}
\;\;\; ≤ftfloor( \;\, k := (i + j) / 2)
if key = L[k] then
    return k
if key < L[k] then
    j := k - 1
else
    i := k + 1 .                         // {#D9534F}{O(1)}

{#D9534F}{O(1)}

{#D9534F}{O(1)}
    return {-1}                          // {#D9534F}{O(1)}
``` #card
?
```text
BinarySearch(L, n, key)
    ≤ft. i := 0
j := n - 1 } O(1)
    {#2A7AE2}{ ≤ft. while i ≤ j do
    k := floor((i + j) / 2)
    if key = L[k] then
        return k
    if key
````
