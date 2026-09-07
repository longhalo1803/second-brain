---
title: "What is the average time complexity of operations in separate chaining under the s..."
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
  - "What is the average time complexity of operations in separate chaining under the s..."
---

# 🎴 What is the average time complexity of operations in separate chaining under the s...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Linear Data Structures & Hashing MOC|📁 Linear Data Structures & Hashing MOC]]

---

### Q: What is the **average time complexity** of operations in separate chaining under the simple uniform hashing assumption? #card

?
Under the simple uniform hashing assumption, the **expected length** of each chained list is exactly equal to the load factor $\alpha = \frac{n}{m}$.

If computing $h(k)$ costs $\Theta(1)$, the expected times (average case) are:

- **Unsuccessful search**: $\Theta(1 + \alpha)$
  (evaluating the hash in constant time and traversing on average an entire list of length $\alpha$).
- **Successful search**: $\Theta(1 + \alpha / 2)$
  (traversing on average half the list before finding the target key).
- **`remove`**: $\Theta(1 + \alpha)$
  (depends on the search time for the node in the list).
- **`insert`**: $O(1)$.
  📌 Fundamental note: if the number of stored elements is proportional to the size of the table, that is, $n \in O(m)$, then the load factor $\alpha \in O(1)$. Consequently, all operations in the average case take constant time **$O(1)$**.
