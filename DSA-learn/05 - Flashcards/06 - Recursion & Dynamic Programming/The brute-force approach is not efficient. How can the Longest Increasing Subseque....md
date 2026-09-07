---
title: "The brute-force approach is not efficient. How can the Longest Increasing Subseque..."
tags:
  - dsa
  - flashcards
  - clrs
  - dynamic-programming
type: reference
status: completed
created: 2026-09-25
updated: 2026-09-25
aliases:
  - "The brute-force approach is not efficient. How can the Longest Increasing Subseque..."
---

# 🎴 The brute-force approach is not efficient. How can the Longest Increasing Subseque...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Recursion & Dynamic Programming MOC|📁 Recursion & Dynamic Programming MOC]]

---

### Q: The brute-force approach is not efficient. How can the **Longest Increasing Subsequence (LIS)** problem be modeled using a **DAG**? #card

?
The idea is to consider one number at a time and try to see if it is possible to extend an increasing sequence that lies to the left of the number.

Given a sequence $A = \langle a_1, a_2, \dots, a_n \rangle$, a DAG $G = (V, E)$ is constructed where:

- There is a **node **for each element of the sequence $A$;
- the nodes are ordered linearly according to the position in which they appear in the sequence.
- There is a directed **edge **from node $i$ to node $j$ (with $i 5 Simple Steps for Solving Dynamic Programming Problems
