---
title: "In stable Counting Sort, how is array C modified and what is the meaning of prefix..."
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
  - "In stable Counting Sort, how is array C modified and what is the meaning of prefix..."
---

# 🎴 In stable Counting Sort, how is array C modified and what is the meaning of prefix...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: In **stable** Counting Sort, how is array $C$ modified and what is the meaning of **prefix sums**? #card

?
After computing the occurrences in $C$ ($C[i] =$ number of occurrences of $i$ in $A$) as for non-stable CS, the values are transformed into **prefix sums (cumulative frequencies)** via the loop:

for i := 1 to k do
C[i] := C[i] + C[i-1]

**Meaning of $C[i]$ after the modification:**
$C[i]$ indicates the **total number of elements in $A$ with value less than or equal to $i$** ($\le i$).

📌 Usefulness: This value indicates that the last element with value equal to $i$ will have to be placed at position (1-based) $C[i]$ of output sorted array $B$ (i.e. at index $C[i] - 1$).
