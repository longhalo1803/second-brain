---
title: "How do hash functions based on Extraction and XOR (binary folding) work"
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
  - "How do hash functions based on Extraction and XOR (binary folding) work"
---

# 🎴 How do hash functions based on Extraction and XOR (binary folding) work

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Linear Data Structures & Hashing MOC|📁 Linear Data Structures & Hashing MOC]]

---

### Q: How do hash functions based on **Extraction** and **XOR (binary folding)** work? #card

?
Both operate on the binary sequence of the key with a table size of $m = 2^p$:

- **Extraction Method:**
  A fixed subset of $p$ bits is selected directly from the binary representation of the key (for example, the last $p$ bits or a middle block).
  📝 Example: if $p=16$ and the binary key has 24 bits, the last 16 bits are extracted as the index in $\{0, \dots, 2^{16}-1\}$.
- **XOR Method:**
  The binary representation of the key is broken into contiguous blocks of $p$ bits each. A modulo-2 sum (bitwise **XOR operation $\oplus$**) is then performed across all blocks.
  📝 Example: for a 3-byte word split into blocks of $p=8$ bits, the 8-bit index is given by:

$$

\text{block}\_1 \oplus \text{block}\_2 \oplus \text{block}\_3

$$

This approach has the advantage of making the computed index dependent on _all_ characters of the key, reducing information loss.
