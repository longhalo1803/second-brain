---
title: "What is the number of operations T(n) executed by the following algorithms (loop b..."
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
  - "What is the number of operations T(n) executed by the following algorithms (loop b..."
---

# 🎴 What is the number of operations T(n) executed by the following algorithms (loop b...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: What is the number of operations $T(n)$ executed by the following algorithms? (loop bounds are both inclusive, and assignment and arithmetic operations are both to be counted as **two separate operations**)

````text
1)\;{aligned}                        // for i = 0 to n-1
    // c := c+1
    // d := d+1
// c := c+d {aligned} 2)\;{aligned}
    // for j = i to n-1
// x := x+1
    // y := y+1 {aligned} 3)\; {aligned}
// y := 1
// while y < n+1
    // x := x+1
    // y := 2y
// return x {aligned}
``` #card
?
```text
1)\;{aligned}                        // for i = 0 to n-1
    // c := c+1
    // d := d+1
// c := c+d {aligned} {aligned}
    // 2 operations
    // 2 operations } Total 4n
        // 2 operations 2 {aligned}
````

$T(n) = 4n + 2 \in O(n) \quad(\text{linear})$
