---
title: "What does the Simple Uniform Hashing assumption state for a hash function"
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
  - "What does the Simple Uniform Hashing assumption state for a hash function"
---

# 🎴 What does the Simple Uniform Hashing assumption state for a hash function

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Linear Data Structures & Hashing MOC|📁 Linear Data Structures & Hashing MOC]]

---

### Q: What does the **Simple Uniform Hashing** assumption state for a hash function? #card

?
A hash function $h$ satisfies the **simple uniform hashing** assumption if it distributes the keys of the universe $U$ uniformly across the $m$ slots of $H$.

Formally, let:

- $P(k)$: the probability that key $k$ is inserted into the table.
- $Q(i)$: the probability that a generic key hashes to the $i$-th slot:

$$

Q(i) = \sum\_{k \in U : h(k) = i} P(k)

$$

$h$ is said to satisfy simple uniform hashing if for every slot $i \in \{0, \dots, m-1\}$:

$$

Q(i) = \frac{1}{m}

$$

⚠️ Warning: simple uniform hashing **does not eliminate collisions**, but it minimizes their average probability. Moreover, it theoretically requires prior knowledge of the probability distribution $P(k)$, a condition that cannot always be verified.
