---
title: "What is the pseudocode algorithm for Make-set(X) in the basic version and its comp..."
tags:
  - dsa
  - flashcards
  - clrs
  - data-structures
type: reference
status: completed
created: 2026-09-25
updated: 2026-09-25
aliases:
  - "What is the pseudocode algorithm for Make-set(X) in the basic version and its comp..."
---

# 🎴 What is the pseudocode algorithm for Make-set(X) in the basic version and its comp...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Linear Data Structures & Hashing MOC|📁 Linear Data Structures & Hashing MOC]]

---

### Q: What is the pseudocode algorithm for `Make-set(X)` in the basic version and its computational complexity? #card

?
The forest initialization algorithm creates an array (the future parent array) DS in which each element is initially its own root (singleton):

```text
Make-set(X)
    {#f74040}{DS} := new_array[1..n]
    for i := 1 to n do
        {#f74040}{DS[i]} := i                // {#D9534F}{≤ftarrow each element is its own root}
    return {#f74040}{DS}
```

**Computational cost**:
$\Theta(n)$ (or $O(n)$), due to the initialization loop of the array of size $n = |X|$.
