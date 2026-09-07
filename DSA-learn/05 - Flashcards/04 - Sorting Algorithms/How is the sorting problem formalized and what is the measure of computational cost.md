---
title: "How is the sorting problem formalized and what is the measure of computational cost"
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
  - "How is the sorting problem formalized and what is the measure of computational cost"
---

# 🎴 How is the sorting problem formalized and what is the measure of computational cost

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: How is the sorting problem formalized and what is the measure of computational cost? #card

?
**Input:**
A sequence of $n$ values $A = \langle a_0, a_1, \dots, a_{n-1} \rangle$ belonging to a totally orderable set.

**Output:**
A permutation $\langle a_0', a_1', \dots, a_{n-1}' \rangle$ of sequence $A$ such that:

$$
a_0' \le a_1' \le \dots \le a_{n-1}'
$$

(that is, sequence $A$ reordered in non-decreasing order).

**Computational cost:**
We count the **comparisons** made between the values of array $A$.
