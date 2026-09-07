---
title: "What is a Direct-Address Table and what are its advantages and disadvantages"
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
  - "What is a Direct-Address Table and what are its advantages and disadvantages"
---

# 🎴 What is a Direct-Address Table and what are its advantages and disadvantages

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Linear Data Structures & Hashing MOC|📁 Linear Data Structures & Hashing MOC]]

---

### Q: What is a **Direct-Address Table** and what are its advantages and disadvantages? #card

?
It is the simplest case of a hash table where the universe of keys $U$ is small and the **identity hash function** is adopted:

$$

h(k) = k

$$

The table has a size equal to the cardinality of the universe: $m = |U|$.

**Advantages:**

- Immediate access, insertion, and deletion in worst-case constant time $O(1)$.
- No collisions: each key corresponds to exactly one unique slot.**Problems / Disadvantages:**
- Applicable **only if the universe $U$ is sufficiently small** (e.g., the 366 days of the year, or Italian provincial capitals).
- If the set of actually stored keys $n$ is much smaller than $|U|$ ($n \ll |U|$), there is an enormous **waste of memory** to maintain unused slots.
