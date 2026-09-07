---
title: "Show the step-by-step execution of Huffman's algorithm for the alphabet Sigma={a,b..."
tags:
  - dsa
  - flashcards
  - clrs
  - sorting
type: reference
status: completed
created: 2026-09-25
updated: 2026-09-25
aliases:
  - "Show the step-by-step execution of Huffman's algorithm for the alphabet Sigma={a,b..."
---

# 🎴 Show the step-by-step execution of Huffman's algorithm for the alphabet Sigma={a,b...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: 📝 Show the step-by-step execution of Huffman's algorithm for the alphabet $\Sigma=\{a,b,c,d,e,f\}$ with frequencies:

$$
a:45, b:13, c:12, d:9, e:16, f:5
$$ #card
?
**Initial state (list sorted in non-decreasing order of frequencies):**
`[(f,5), (d,9), (c,12), (b,13), (e,16), (a,45)]`

1. Extracts `(f,5)` and `(d,9)` $\to$ creates `(-,14)`.
    Sorted list: `[(c,12), (b,13), (-,14), (e,16), (a,45)]`

2. Extracts `(c,12)` and `(b,13)` $\to$ creates `(-,25)`.
    Sorted list: `[(-,14), (e,16), (-,25), (a,45)]`

3. Extracts `(-,14)` and `(e,16)` $\to$ creates `(-,30)`.
    Sorted list: `[(-,25), (-,30), (a,45)]`

4. Extracts `(-,25)` and `(-,30)` $\to$ creates `(-,55)`.
    Sorted list: `[(a,45), (-,55)]`

5. Extracts `(a,45)` and `(-,55)` $\to$ creates root `(-,100)`.

**Resulting codewords:**
• $a = 0$ (1 bit)
• $c = 100$ (3 bits)
• $b = 101$ (3 bits)
• $f = 1100$ (4 bits)
• $d = 1101$ (4 bits)
• $e = 111$ (3 bits)

┉┉┉┉┉┉┉┉┉┉┉┉┉┉┉┉┉┉┉┉┉┉┉┉┉┉┉┉

┉┉┉┉┉┉┉┉┉┉┉┉┉┉┉┉┉┉┉┉┉┉┉┉┉┉┉┉

┉┉┉┉┉┉┉┉┉┉┉┉┉┉┉┉┉┉┉┉┉┉┉┉┉┉┉┉

┉┉┉┉┉┉┉┉┉┉┉┉┉┉┉┉┉┉┉┉┉┉┉┉┉┉┉┉

┉┉┉┉┉┉┉┉┉┉┉┉┉┉┉┉┉┉┉┉┉┉┉┉┉┉┉┉

┉┉┉┉┉┉┉┉┉┉┉┉┉┉┉┉┉┉┉┉┉┉┉┉┉┉┉┉

┉┉┉┉┉┉┉┉┉┉┉┉┉┉┉┉┉┉┉┉┉┉┉┉┉┉┉┉
$$
