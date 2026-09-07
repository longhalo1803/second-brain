---
title: "What are the best and worst cases for the following problem"
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
  - "What are the best and worst cases for the following problem"
---

# 🎴 What are the best and worst cases for the following problem

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Complexity & Fundamentals MOC|📁 Complexity & Fundamentals MOC]]

---

### Q: What are the best and worst cases for the following problem?

Given a sequence of `n` integers `A = A[0]A[1]...A[n-1]` and a number `x`, determine if `x` is present in `A` and, if so, at what position:
Search(A,x)
i := 0
while i #card
?
****Best case****: when `x = A[0]` → the number of operations is a _constant _(independent of `n`).
****Worst case****: when `x` does not appear in `A`, because it is necessary to compare all elements of the list with `x` → the number of operations is _`n`_ multiplied by a constant.

**There are instances** where the number of executed operations is **constant**, and **there are no instances** for which the number of operations is more than **linear **with respect to how many numbers compose the sequence given as input.

The worst case gives us an _upper bound_ on the number of operations to execute for any instance.
