---
title: "What is a prefix code (or prefix-free code) and what important property does it gu..."
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
  - "What is a prefix code (or prefix-free code) and what important property does it gu..."
---

# 🎴 What is a prefix code (or prefix-free code) and what important property does it gu...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Complexity & Fundamentals MOC|📁 Complexity & Fundamentals MOC]]

---

### Q: What is a prefix code (or prefix-free code) and what important property does it guarantee? #card

?
A code is called a **prefix code** (or _prefix-free code_) if **no codeword is a prefix of another codeword** in the alphabet.

Prefix codes guarantee that any encoded sequence of bits can be decoded **uniquely and without ambiguity**, by reading the sequence from left to right (instantaneous decoding).

📝 Example:
• **Code 2 (Prefix code):** $a=0, b=100, c=101, d=111, e=1100, f=1101$. No codeword is a prefix of another. The string `100010001010` is decoded uniquely as `100|0|100|0|101|0` $\to$ `babaca`.
• **Code 3 (NOT prefix-free):** $b=1$ is a prefix of $c=10$ and $e=100$; decoding is ambiguous.

        character
        a
        b
        c
        d
        e
        f




        Code 2
        0
        100
        101
        111
        1100
        1101


        Code 3
        0
        1
        10
        11
        100
        101
