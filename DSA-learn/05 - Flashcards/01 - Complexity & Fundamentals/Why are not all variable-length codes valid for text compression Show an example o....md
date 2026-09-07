---
title: "Why are not all variable-length codes valid for text compression Show an example o..."
tags:
  - dsa
  - flashcards
  - clrs
  - complexity
type: reference
status: completed
created: 2026-09-25
updated: 2026-09-25
aliases:
  - "Why are not all variable-length codes valid for text compression Show an example o..."
---

# 🎴 Why are not all variable-length codes valid for text compression Show an example o...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Complexity & Fundamentals MOC|📁 Complexity & Fundamentals MOC]]

---

### Q: Why are not all variable-length codes valid for text compression? Show an example of ambiguity in decoding. #card

?
A generic variable-length code can be **ambiguous** during decoding if the same sequence of bits can be interpreted in multiple different ways.

⚠️ Note: even if a code reduces the theoretical file size, if it cannot be uniquely decoded it is unusable (it would cause information loss).

📝 Example (Code 3, ambiguous):

      character
      a
      b
      c
      d
      e
      f
      |F|




      frequency
      45%
      13%
      12%
      16%
      9%
      5%
      2.24n


      Code 3
      0
      1
      10
      11
      100
      101
      1.56n

Assignment: $a=0, b=1, c=10, d=11, e=100, f=101$.
If we receive the bit sequence `100010001010`, there are multiple possible decodings:
• `1|0|0|0|1|0|0|0|1|0|1|0` $\to$ `baaabaaababa`
• `10|0|0|10|0|0|10|1|0` $\to$ `caacaacba`
• `100|0|10|0|0|101|0` $\to$ `eacaafa`

The ambiguity arises from the fact that some codewords (e.g., $b=1$, $c=10$) are ****prefixes**** of other codewords (e.g., $c=10$, $e=100$).
