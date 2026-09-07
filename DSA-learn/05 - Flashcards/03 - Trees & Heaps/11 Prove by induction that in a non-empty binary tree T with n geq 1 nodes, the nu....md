---
title: "11 Prove by induction that in a non-empty binary tree T with n geq 1 nodes, the nu..."
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
  - "11 Prove by induction that in a non-empty binary tree T with n geq 1 nodes, the nu..."
---

# 🎴 11 Prove by induction that in a non-empty binary tree T with n geq 1 nodes, the nu...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: 📝 11 Prove by induction that in a non-empty binary tree $T$ with $n \geq 1$ nodes, the number of leaves $f(n)$ is equal to $1$ plus the number of internal nodes with exactly two children $i(n)$:

$$

f(n) = i(n) + 1

$$

#card
?
****Proof by Induction on $n$ (number of nodes)**:**

**1. Base Case ($n = 1$):**
The tree consists of a single leaf (the root).
It has $f(1) = 1$ and $i(1) = 0$ internal nodes with two children.
It holds that: $f(1) = 1 = 0 + 1 = i(1) + 1$. The base case is verified.

**2. Inductive Hypothesis:**
Assume that the property holds for every binary tree with $n - 1$ nodes:

$$

f(n - 1) = i(n - 1) + 1

$$

**3. Inductive Step:**
A tree $T(n)$ with $n$ nodes is obtained from a tree $T(n-1)$ by adding a new leaf node. Consider where the leaf is added:

- **Case A (added as child of a leaf of $T(n-1)$):**
  The leaf in $T(n-1)$ becomes an internal node with only one child, while the new node becomes a leaf.
  The total number of leaves does not change: $f(n) = f(n-1)$.
  The number of nodes with 2 children does not change: $i(n) = i(n-1)$.
  By inductive hypothesis:

$$

f(n) = f(n-1) = i(n-1) + 1 = i(n) + 1

$$

- **Case B (added as child of an internal node with 1 child in $T(n-1)$):**
  The new leaf increases the total leaves by 1: $f(n) = f(n-1) + 1$.
  The parent becomes an internal node with 2 children, so: $i(n) = i(n-1) + 1$.
  Substituting the inductive hypothesis:

$$

f(n) = f(n-1) + 1 = (i(n-1) + 1) + 1 = i(n) + 1

$$

The property is therefore proven for all $n \ge 1$.
