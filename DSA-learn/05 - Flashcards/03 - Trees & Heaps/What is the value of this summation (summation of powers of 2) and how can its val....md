---
title: "What is the value of this summation (summation of powers of 2) and how can its val..."
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
  - "What is the value of this summation (summation of powers of 2) and how can its val..."
---

# 🎴 What is the value of this summation (summation of powers of 2) and how can its val...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Trees & Heaps MOC|📁 Trees & Heaps MOC]]

---

### Q: What is the value of this summation (summation of powers of 2) and how can its value be found analytically and with binary code?

$$

\sum\_{i=0}^{n} 2^i = \;?

$$

#card
?
**1. Analytical solution (geometric progression)**
Analytically, the summation is recognized as the sum of the first $n+1$ terms of a geometric progression with ratio $q = 2$.

The general formula for the sum of a geometric progression is:

```text
_{i=0}^{n} q^i = {1 - q^{n+1}}{1 - q} (for q ≠q 1) {gray} (or {q^{n+1} - 1}{q - 1})
```

Substituting $q = 2$:

$$

\sum\_{i=0}^{n} 2^i = \frac{1 - 2^{n+1}}{1 - 2} = \frac{1 - 2^{n+1}}{-1} = \frac{2^{n+1} - 1}{1} = 2^{n+1} - 1

$$

---

**2. Intuitive approach via binary system**
A summation of powers of two corresponds exactly to the representation of a binary number composed entirely of $1$ digits.

Example and review of binary-to-decimal conversion:
Let's take the binary number $1011001_2$. Assigning weights (exponents from right to left starting from $0$), we have:

$$

1011001_2 = 1 \cdot 2^0 + 0 \cdot 2^1 + 0 \cdot 2^2 + 1 \cdot 2^3 + 1 \cdot 2^4 + 0 \cdot 2^5 + 1 \cdot 2^6

$$

Expansion of the summation: if we apply this concept to our summation (using the variable $n$ or $n$ as indicated in the text), we obtain a series in which all coefficients are equal to $1$:

$$

\sum\_{i=0}^{n} 2^i = \textcolor{orange}{1} \cdot 2^0 + \textcolor{orange}{1} \cdot 2^1 + \textcolor{orange}{1} \cdot 2^2 + \textcolor{orange}{1} \cdot 2^3 + \dots + \textcolor{orange}{1} \cdot 2^n

$$

In binary format, this number is represented by a sequence of $n+1$ ones:

$$

\sum*{i=0}^{n} 2^i = \underbrace{111 \dots 111_2}*{n+1 \text{ digits}}

$$

To find the value of this number, we add $1$ (i.e. $1_2$) in binary. When adding $1$ to a string of only $1$s, a continuous carry is generated that shifts the unit to the next position ($n+1$), setting all previous ones to zero:

$$

\begin{array}{rccccccl}
\color{teal}\text{(carries)} & \color{teal}\scriptstyle 1 & \color{teal}\scriptstyle 1 & \color{teal}\scriptstyle 1 & \color{teal}\dots & \color{teal}\scriptstyle 1 & & \\
& & 1 & 1 & \dots & 1 & 1 & + \\
& & & & & & 1 & = \\
\hline
& 1 & 0 & 0 & \dots & 0 & 0 &
\end{array}

$$

The result obtained consists of a $1$ followed by $n+1$ zeros. In base 2, this number is exactly equal to:

$$

1\underbrace{00\dots0}\_{n+1 \text{ zeros}} = 2^{n+1}

$$

Since we added $1$ to obtain this precise result, the original value of the summation will be equal to that result minus $1$:

$$

\sum\_{i=0}^{n} 2^i = 2^{n+1} - 1

$$
