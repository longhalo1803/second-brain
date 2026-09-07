---
title: "How are the formulas for Parent(i), LeftChild(i), and RightChild(i) proven algebra..."
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
  - "How are the formulas for Parent(i), LeftChild(i), and RightChild(i) proven algebra..."
---

# 🎴 How are the formulas for Parent(i), LeftChild(i), and RightChild(i) proven algebra...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Linear Data Structures & Hashing MOC|📁 Linear Data Structures & Hashing MOC]]

---

### Q: How are the formulas for Parent(i), LeftChild(i), and RightChild(i) proven algebraically? #card

?
Let $n' = 2^\ell - 1$ be the number of nodes present up to level $\ell-1$. The position of element $H[i]$ at level $\ell$ with left offset $\ell_s$ is $i = n' + \ell_s$.

Its left child is at level $\ell+1$ with offset $2\ell_s$. Its position in the array is:

$$

\text{pos} = i + \ell*d + 2 \cdot \ell_s + 1 = i + \underbrace{(\ell_d + \ell_s + 1)}*{\text{# nodes at level } \ell} + \ell*s = i + (n' + 1) + \ell_s = i + \underbrace{(n' + \ell_s)}*{= i} + 1 = 2i + 1

$$

**Proof of the parent formula**:
• If $i$ is a **left child** (**_odd_** index):
$i = 2j + 1 \implies j = \frac{i-1}{2} = \left\lceil \frac{i}{2} \right\rceil - 1$

• If $i$ is a **right child** (**_even_** index):
$i = 2(j+1) = 2j+2 \implies j = \frac{i}{2} - 1 = \left\lceil \frac{i}{2} \right\rceil - 1$

In both cases the formula is unified by $\left\lceil \frac{i}{2} \right\rceil - 1$.
