---
title: "What are the formulas to calculate the indices of Parent, Left Child, and Right Ch..."
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
  - "What are the formulas to calculate the indices of Parent, Left Child, and Right Ch..."
---

# 🎴 What are the formulas to calculate the indices of Parent, Left Child, and Right Ch...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Linear Data Structures & Hashing MOC|📁 Linear Data Structures & Hashing MOC]]

---

### Q: What are the formulas to calculate the indices of Parent, Left Child, and Right Child in the implicit array representation? #card

?
Given a node located at index $i$ of array `H` (with 0-based indexing):

```text
Parent(i) = ≤ft {i}{2} - 1 {gray}≤ft(= ≤ft {i-1}{2} )^*
```

$$

\text{LeftChild}(i) = 2i + 1

$$

$$

\text{RightChild}(i) = 2(i+1) = 2i + 2

$$

📌 Note:
At the hardware level, multiplications and divisions by 2 are executed in constant time $\mathcal{O}(1)$ via binary shift operations (`i > 1`).

*Proof that the two formulas for parent are equivalent
To verify the relationship between the two expressions for every integer $i$, we can separately analyze the cases where $i$ is even and those where $i$ is odd.__Case 1: **$i$** is even__Let $i = 2k$ with $k \in \mathbb{Z}$:

- **Expression 1: ****$\small\left\lceil \frac{2k}{2} \right\rceil - 1 = \lceil k \rceil - 1 = k - 1$**
- **Expression 2: ****$\small\left\lfloor \frac{2k-1}{2} \right\rfloor = \left\lfloor k - \frac{1}{2} \right\rfloor = k - 1$**Both sides yield the result $k - 1$.__Case 2: **$i$** is odd__Let $i = 2k + 1$ with $k \in \mathbb{Z}$:
- **Expression 1: **$\small\left\lceil \frac{2k+1}{2} \right\rceil - 1 = \left\lceil k + \frac{1}{2} \right\rceil - 1 = (k + 1) - 1 = k$
- **Expression 2: **$\small\left\lfloor \frac{(2k+1)-1}{2} \right\rfloor = \left\lfloor \frac{2k}{2} \right\rfloor = \lfloor k \rfloor = k$Both sides yield the result $k$.**Evaluation on numerical values:**
- For $i = 1$:
- $\left\lceil \frac{1}{2} \right\rceil - 1 = 1 - 1 = 0$
- $\left\lfloor \frac{1-1}{2} \right\rfloor = \left\lfloor 0 \right\rfloor = 0$
- For $i = 2$:
- $\left\lceil \frac{2}{2} \right\rceil - 1 = 1 - 1 = 0$
- $\left\lfloor \frac{2-1}{2} \right\rfloor = \left\lfloor \frac{1}{2} \right\rfloor = 0$
- For $i = 3$:
- $\left\lceil \frac{3}{2} \right\rceil - 1 = 2 - 1 = 1$
- $\left\lfloor \frac{3-1}{2} \right\rfloor = \left\lfloor 1 \right\rfloor = 1$The equality $\left\lceil \frac{i}{2} \right\rceil - 1 = \left\lfloor \frac{i-1}{2} \right\rfloor$ holds for all integers $i$; therefore, the two expressions are completely equivalent.
