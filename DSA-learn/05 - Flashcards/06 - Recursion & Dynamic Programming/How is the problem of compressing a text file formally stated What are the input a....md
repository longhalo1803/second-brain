---
title: "How is the problem of compressing a text file formally stated What are the input a..."
tags:
  - dsa
  - flashcards
  - clrs
  - dynamic-programming
type: reference
status: completed
created: 2026-09-25
updated: 2026-09-25
aliases:
  - "How is the problem of compressing a text file formally stated What are the input a..."
---

# 🎴 How is the problem of compressing a text file formally stated What are the input a...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Recursion & Dynamic Programming MOC|📁 Recursion & Dynamic Programming MOC]]

---

### Q: How is the problem of compressing a text file formally stated? What are the input and output of the problem? #card

?
**Input:**
• A finite alphabet $\Sigma$ of characters.
• A text file $F$ consisting of $n$ characters belonging to $\Sigma$.
• Frequency $f(c)$ of occurrence for each character in the alphabet $c \in \Sigma$.

**Output:**
A binary encoding for each character $\text{cod}: \Sigma \to \{0,1\}^*$ such that the total size of the compressed file $|F|$ is ****minimum****:

$$

|F| = \sum\_{c \in \Sigma} f(c) \cdot |\text{cod}(c)|

$$

See also video Huffman Codes: An Information Theory Perspective
