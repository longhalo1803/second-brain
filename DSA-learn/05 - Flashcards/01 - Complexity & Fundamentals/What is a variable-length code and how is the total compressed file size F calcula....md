---
title: "What is a variable-length code and how is the total compressed file size F calcula..."
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
  - "What is a variable-length code and how is the total compressed file size F calcula..."
---

# 🎴 What is a variable-length code and how is the total compressed file size F calcula...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Complexity & Fundamentals MOC|📁 Complexity & Fundamentals MOC]]

---

### Q: What is a variable-length code and how is the total compressed file size $|F|$ calculated (write the formula)? (_ignoring how such a code is exactly obtained, for now_) #card

?
In a **variable-length code**, different characters can be encoded with binary sequences of different lengths ($|\text{cod}(c)|$).

**Calculation of the total file size:**
If the character frequencies in a file $F$ of $n$ characters are expressed as percentages, the total size $|F|$ is given by:

$$
|F| = \sum_{c \in \Sigma} f(c) \cdot |\text{cod}(c)|
$$

which is:

$$
|F| = \left( \sum_{c \in \Sigma} \text{freq}_{\%}(c) \cdot |\text{cod}(c)| \right) \cdot \frac{n}{100} \text{ bits}
$$

📝 Example (Code 2 on $\Sigma=\{a,b,c,d,e,f\}$):

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



      ASCII
      01100001
      01100010
      0110011
      01100100
      01100101
      01100110
      8n


      Code 1
      000
      001
      010
      011
      100
      101
      3n


      Code 2
      0
      100
      101
      111
      1100
      1101
      2.24n

Frequencies: $a: 45\%, b: 13\%, c: 12\%, d: 9\%, e: 16\%, f: 5\%$.
Encodings: $a=0$ (1 bit), $b=100$ (3 bits), $c=101$ (3 bits), $d=111$ (3 bits), $e=1100$ (4 bits), $f=1101$ (4 bits).
Calculation:

$$
\begin{aligned} \vert{}F\vert{} &= 0.45n \cdot 1 + 0.13n \cdot 3 + 0.12n \cdot 3 + 0.16n \cdot 3 + 0.09n \cdot 4 + 0.05n \cdot 4 \\ &= (45 \cdot 1 + 13 \cdot 3 + 12 \cdot 3 + 16 \cdot 3 + 9 \cdot 4 + 5 \cdot 4) \frac{n}{100} \\ &= (45 + 39 + 36 + 48 + 36 + 20) \frac{n}{100} = 2.24n \text{ bits} \end{aligned}
$$

Compared to the fixed-length code ($3n$) or ASCII ($8n$), significant space savings are achieved.

**Decoding:** $100010001010 → 100|0|100|0|101|0 → babaca$
