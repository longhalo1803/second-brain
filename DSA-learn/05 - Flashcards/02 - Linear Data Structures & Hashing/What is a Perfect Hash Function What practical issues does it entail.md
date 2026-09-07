---
title: "What is a Perfect Hash Function What practical issues does it entail"
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
  - "What is a Perfect Hash Function What practical issues does it entail"
---

# 🎴 What is a Perfect Hash Function What practical issues does it entail

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Linear Data Structures & Hashing MOC|📁 Linear Data Structures & Hashing MOC]]

---

### Q: What is a **Perfect Hash Function**? What practical issues does it entail? #card

?
A hash function $h: U \to \{0, \dots, m-1\}$ is called **perfect** if it is **injective**, that is:

$$

\forall k_1, k_2 \in U : k_1 \neq k_2 \implies h(k_1) \neq h(k_2)

$$

With a perfect function, distinct keys are guaranteed to map to distinct slots in the table.

📝 Example: students enrolled over a five-year period with student IDs in the contiguous range $U = \{234714, \dots, 23800\}$. One defines $h(k) = k - 234714$ with size $m = 23800 - 234714 + 1$.

**Practical issues:**

- It is often **difficult or impossible to implement** if the exact set of keys is not strictly known in advance.
- Requires $m \ge |U|$, which can be prohibitive if $|U|$ is huge.
- If the keys actually used are few compared to $|U|$, it leads to significant memory waste.
