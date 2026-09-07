---
title: "In Hash Tables with separate chaining, how are insert, search, and deletion operat..."
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
  - "In Hash Tables with separate chaining, how are insert, search, and deletion operat..."
---

# 🎴 In Hash Tables with separate chaining, how are insert, search, and deletion operat...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Linear Data Structures & Hashing MOC|📁 Linear Data Structures & Hashing MOC]]

---

### Q: In Hash Tables with separate chaining, how are **insert**, **search**, and **deletion** operations implemented? #card

?
Assuming that computing the hash function takes $\Theta(1)$ time:

- **`insert(D, k, v)`**:
  $i = h(k)$ is computed. The new pair $(k, v)$ is prepended (**head insertion**) to the linked list $H[i]$.
  Cost: **$O(1)$** in the worst case (assuming the key is not already present or uniqueness checks are not required).
- **`lookup(D, k)`**:
  $i = h(k)$ is computed and a **linear scan** is performed within the list pointed to by $H[i]$ until the target key is found or the end of the list is reached.
- **`remove(D, k)`**:
  $i = h(k)$ is computed, the node with key $k$ is searched in list $H[i]$ and unlinked from the list itself.
