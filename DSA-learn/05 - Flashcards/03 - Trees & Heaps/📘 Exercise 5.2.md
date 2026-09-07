---
title: "📘 Exercise 5.2"
tags:
  - dsa
  - flashcards
  - clrs
  - trees-heaps
type: reference
status: completed
created: 2026-09-25
updated: 2026-09-25
aliases:
  - "📘 Exercise 5.2"
---

# 🎴 📘 Exercise 5.2

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: 📘 Exercise 5.2

Consider an abstract data type `Foo` that stores a multiset of values $\{0, 1, 2\}$ with the following primitives:

- `new_Foo(n)`: returns a new instance of Foo holding at most $n$ values.
- `insert(Foo, x)`: inserts value $x \in \{0, 1, 2\}$.
- `delete(Foo, x)`: deletes one occurrence of $x$, if present.
- `count(Foo, x)`: returns the number of occurrences of $x$.Provide an implementation where values are stored in an array and all operations run in $O(1)$ worst-case time. #card
  ?
  **Reasoning:**
  Since the domain of elements is restricted to $\{0, 1, 2\}$, we can track the frequency of each value in an array of size 3, while keeping total size $\le n$. Alternatively, to explicitly store elements in an array $A[0 \dots n-1]$, we can maintain counts and store inserted values consecutively.

**Data Structure Representation:**
Foo consists of:

- An array $C[0 \dots 2]$ of size 3 where $C[x]$ stores the frequency of value $x$.
- An integer $max\_n$ representing the maximum capacity.
- An integer $size = C[0] + C[1] + C[2]$ storing the current number of elements.
  **Fseudocode:**

```text
Function new_Foo(n):
    F ≤ftarrow new Object()
    F.C[] ≤ftarrow array of size 3 initialized to [0, 0, 0]
    F.max_n ≤ftarrow n; \; F.size ≤ftarrow 0
    return F

Frocedure insert(F, x):
    if F.size  0 then
        F.C[x] ≤ftarrow F.C[x] - 1
        F.size ≤ftarrow F.size - 1

Function count(F, x):
    if x ∈ {0, 1, 2} then return F.C[x]
    return 0
```

**Complexity:**
All operations perform a constant number of direct array accesses and arithmetic operations, running in $O(1)$ time and using $O(1)$ auxiliary memory.
