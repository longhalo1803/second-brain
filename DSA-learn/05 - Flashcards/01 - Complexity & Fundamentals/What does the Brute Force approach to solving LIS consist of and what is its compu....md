---
title: "What does the Brute Force approach to solving LIS consist of and what is its compu..."
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
  - "What does the Brute Force approach to solving LIS consist of and what is its compu..."
---

# 🎴 What does the Brute Force approach to solving LIS consist of and what is its compu...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Complexity & Fundamentals MOC|📁 Complexity & Fundamentals MOC]]

---

### Q: What does the **Brute Force** approach to solving LIS consist of and what is its computational complexity? #card

?
For each possible subsequence of $A$, check whether it is increasing or not, keeping track of the longest increasing subsequence found up to that point.

Some brute-force attempts:

**Computational Cost:**
Since a sequence of length $n$ has $2^n$ possible subsets of indices, the number of candidate subsequences to check is exponential, leading to a complexity of **$O(2^n)$**.
