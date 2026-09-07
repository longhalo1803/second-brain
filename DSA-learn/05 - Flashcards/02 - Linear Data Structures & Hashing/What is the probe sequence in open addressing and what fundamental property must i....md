---
title: "What is the probe sequence in open addressing and what fundamental property must i..."
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
  - "What is the probe sequence in open addressing and what fundamental property must i..."
---

# 🎴 What is the probe sequence in open addressing and what fundamental property must i...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Linear Data Structures & Hashing MOC|📁 Linear Data Structures & Hashing MOC]]

---

### Q: What is the **probe sequence** in open addressing and what fundamental property must it satisfy? #card

?
In open addressing, the hash function is extended to take the **probe number** $i \in \{0, 1, \dots, m-1\}$ as a second parameter:

$$

h: U \times \{0, 1, \dots, m-1\} \to \{0, 1, \dots, m-1\}

$$

For each key $k$, the probe sequence is the ordered sequence of indices to examine:

$$

\langle h(k, 0), h(k, 1), h(k, 2), \dots, h(k, m-1) \rangle

$$

**Fundamental property:**
The probe sequence must be a **permutation** of all table indices $\{0, 1, \dots, m-1\}$, ensuring that:

```text
h(k, i) ≠q h(k, j) i ≠q j
```

This guarantees that if there are empty slots in the table, the algorithm will certainly find one without getting trapped in a subset of positions.
