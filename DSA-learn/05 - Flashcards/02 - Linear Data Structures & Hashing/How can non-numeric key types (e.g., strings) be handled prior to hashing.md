---
title: "How can non-numeric key types (e.g., strings) be handled prior to hashing"
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
  - "How can non-numeric key types (e.g., strings) be handled prior to hashing"
---

# 🎴 How can non-numeric key types (e.g., strings) be handled prior to hashing

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Linear Data Structures & Hashing MOC|📁 Linear Data Structures & Hashing MOC]]

---

### Q: How can non-numeric key types (e.g., **strings**) be handled prior to hashing? #card

?
Whatever the key type (e.g., strings, records, objects), keys can always be converted into **non-negative integer numeric values** that can be manipulated arithmetically.

📝 Example: for a character string like `"DOG"`, one can concatenate the ASCII/binary codes of individual characters:

- `'D'` $\to 01000100_2 = 68$
- `'O'` $\to 01001111_2 = 79$
- `'G'` $\to 01000111_2 = 71$The overall binary representation is the concatenated 24-bit sequence:
  `01000100 01001111 01000111`.

⚠️ Warning: this transformation is merely an **encoding**, not the actual hash function itself, which must then map this integer into the range $[0 \dots m-1]$.
