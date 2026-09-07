---
title: "In the division method (h(k) = k bmod m), why should m = 2^p not be chosen"
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
  - "In the division method (h(k) = k bmod m), why should m = 2^p not be chosen"
---

# 🎴 In the division method (h(k) = k bmod m), why should m = 2^p not be chosen

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Linear Data Structures & Hashing MOC|📁 Linear Data Structures & Hashing MOC]]

---

### Q: In the division method ($h(k) = k \bmod m$), why **should $m = 2^p$ not be chosen**? #card

?
If the table size is chosen to be a power of two, $m = 2^p$, then the hash value $h(k) = k \bmod 2^p$ matches exactly the **last $p$ binary digits (least significant bits)** of $k$.

The resulting issues are:

- **Pattern dependence:** if keys exhibit regularities or common patterns in their lowest bits (e.g., pointers aligned to multiples of 4 ending in `00`, or even numerical identifiers), many keys will collide into the same slot.
- **Entropy loss:** all information contained in the higher-order bits (from the $p$-th bit onward) is completely discarded, drastically degrading key distribution.📝 Example: with $m = 2^3 = 8$, $h(k) = k \bmod 8$ depends only on the last 3 bits. Values $2 = 000010_2$, $10 = 001010_2$, and $26 = 011010_2$ all end with `010` and systematically collide in slot $2$.
