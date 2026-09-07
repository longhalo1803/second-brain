---
title: "What is the formulation of the sorting problem solved by Counting Sort and what co..."
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
  - "What is the formulation of the sorting problem solved by Counting Sort and what co..."
---

# 🎴 What is the formulation of the sorting problem solved by Counting Sort and what co...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: What is the formulation of the sorting problem solved by **Counting Sort** and what constraint characterizes it? #card

?
**Input:** A sequence of $n$ natural numbers $A = \langle a_0, a_1, \dots, a_{n-1} \rangle$ such that $0 \le a_i \le k, \, \forall i \in \{0, 1, \dots, n-1\}$.
**Output:** A permutation $\langle a_0', a_1', \dots, a_{n-1}' \rangle$ of sequence $A$ sorted in non-decreasing order ($a_0' \le a_1' \le \dots \le a_{n-1}'$).

⚠️ Fundamental constraint and feature: **NO comparisons are made** between the elements of $A$.

📌 Note:
The algorithm assumes that all input elements are integers within a known range $[0, k]$.
