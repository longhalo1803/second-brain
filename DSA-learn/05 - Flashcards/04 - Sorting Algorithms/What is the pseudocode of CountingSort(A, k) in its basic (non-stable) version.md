---
title: "What is the pseudocode of CountingSort(A, k) in its basic (non-stable) version"
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
  - "What is the pseudocode of CountingSort(A, k) in its basic (non-stable) version"
---

# 🎴 What is the pseudocode of CountingSort(A, k) in its basic (non-stable) version

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: 🟢 What is the pseudocode of `CountingSort(A, k)` in its basic (non-stable) version? #card

?

```text
CountingSort(A, k)
    n := length(A)
    create C[0..k]
    for i := 0 to k do                   // {#D9534F}{(k)}
        C[i] := 0
    [#2EAD6B, 1pt]{ for j := 0 to n-1 do} // {#D9534F}{(n)}
        [#2EAD6B, 1pt]{ C[A[j]] := C[A[j]] + 1}
    j := 0
    [#5C6BC0, 1pt]{ for i := 0 to k do}  // {#D9534F}{(n+k)}
        [#5C6BC0, 1pt]{ while C[i] > 0 do}
            [#5C6BC0, 1pt]{ A[j] := i}
            [#5C6BC0, 1pt]{ j := j + 1}
            [#5C6BC0, 1pt]{ C[i] := C[i] - 1}
```

**Time complexity**: $\Theta(n + k)$.
**Auxiliary space complexity**: $\Theta(k)$.

https://visualgo.net/en/sorting?mode=Counting (click Sort on bottom left)
