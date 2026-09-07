---
title: "How does Linear Probing work in open addressing"
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
  - "How does Linear Probing work in open addressing"
---

# 🎴 How does Linear Probing work in open addressing

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Linear Data Structures & Hashing MOC|📁 Linear Data Structures & Hashing MOC]]

---

### Q: How does **Linear Probing** work in open addressing? #card

?
In **linear probing**, the extended hash function is defined as:

$$

h(k, i) = (h'(k) + c \cdot i) \bmod m

$$

where $h'(k)$ is an ordinary auxiliary hash function, $i \in \{0, \dots, m-1\}$ is the probe number, and $c$ is an integer constant (frequently $c=1$).

With $c = 1$, the sequence of probed slots is simply:

$$

\begin{aligned} h(k, 0) &= h'(k) \bmod m \\ h(k, 1) &= (h'(k) + 1) \bmod m \\ h(k, 2) &= (h'(k) + 2) \bmod m \\ &\dots \end{aligned}

$$

Contiguous cells of the table are examined in circular order, wrapping back to the beginning (index 0) when exceeding $m-1$.
