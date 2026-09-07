---
title: "What are the three fundamental observations in the problem of text file compressio..."
tags:
  - dsa
  - flashcards
  - clrs
  - trees-heaps
type: reference
status: completed
created: 2026-09-25
updated: 2026-09-25
aliases:
  - "What are the three fundamental observations in the problem of text file compressio..."
---

# 🎴 What are the three fundamental observations in the problem of text file compressio...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: What are the three fundamental observations in the problem of text file compression using an ad-hoc code? #card

?

- **Tree representation:** the prefix code is efficiently represented by a binary coding tree (leaves = characters, edges = 0/1 bits).
- **Ad-hoc code:** every text file has its own specific ad-hoc code optimized for the actual frequencies of the characters present in it.
- **Inclusion of the tree for decoding:** since each file has its own customized code, the compressed file _must be accompanied by the coding tree_ (or the frequency table) for decoding to take place.
