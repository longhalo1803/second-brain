---
title: "What is a fixed-length code for a text file and how many bits are needed per chara..."
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
  - "What is a fixed-length code for a text file and how many bits are needed per chara..."
---

# 🎴 What is a fixed-length code for a text file and how many bits are needed per chara...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Complexity & Fundamentals MOC|📁 Complexity & Fundamentals MOC]]

---

### Q: What is a fixed-length code for a text file and how many bits are needed per character given an alphabet $\Sigma$? #card

?
In a **fixed-length code**, every character in the alphabet $\Sigma$ is assigned a binary sequence of the same length.

• **Number of bits needed per character:** $\lceil \log_2 |\Sigma| \rceil$ bits.
• **File size:** $|F| = n \cdot \lceil \log_2 |\Sigma| \rceil$ bits.

📝 Example ($\Sigma = \{a,b,c,d,e,f\}$):
Since $|\Sigma| = 6$, $\lceil \log_2 6 \rceil = 3$ bits per character are needed (e.g., $a=000, b=001, c=010, d=011, e=100, f=101$).
The total size of the compressed file will be $|F| = 3n$ bits.

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

📌 Note:
The standard **ASCII** code is an example of a fixed-length code that uses 8 bits per character, leading to a file size of $8n$ bits.

**Decoding:
**It is immediate and unambiguous: every continuous sequence of $\lceil \log_2 |\Sigma| \rceil$ bits of the compressed file corresponds exactly to one character of the alphabet.
