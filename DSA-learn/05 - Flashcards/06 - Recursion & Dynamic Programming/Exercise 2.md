---
title: "Exercise 2"
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
  - "Exercise 2"
---

# 🎴 Exercise 2

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Recursion & Dynamic Programming MOC|📁 Recursion & Dynamic Programming MOC]]

---

### Q: 📝📍 Exercise 2

Consider a file $F$ of length $n$ characters composed only of the symbols and frequencies indicated below. Calculate the percentage saving (possibly rounded to the nearest integer) obtained by compressing $F$ with a Huffman code compared to a minimal fixed-length code.

1. $n = 70000$ and the characters $\{a, b, c, d, e\}$ are associated in order with frequencies $\{7, 9, 8, 53, 23\}$.
2. $n = 60000$ and the characters $\{a, b, c, d, e\}$ are associated in order with frequencies $\{14, 8, 65, 5, 8\}$.
3. $n = 30000$ and the characters $\{a, b, c, d, e, f\}$ are associated in order with frequencies $\{45, 20, 7, 6, 14, 8\}$.
4. $n = 50000$ and the characters $\{a, b, c, d, e, f\}$ are associated in order with frequencies $\{8, 35, 5, 24, 23, 5\}$.
5. $n = 10000$ and the characters $\{a, b, c, d, e, f\}$ are associated in order with frequencies $\{46, 11, 8, 11, 14, 10\}$.
6. $n = 60000$ and the characters $\{a, b, c, d, e, f\}$ are associated in order with frequencies $\{13, 48, 15, 6, 10, 8\}$.

📌 Note:
In this case it is not necessary to find a specific Huffman code; any one is sufficient, as what matters is not the code itself, but the length of the encoding associated with each individual character.
Indeed, different Huffman codes may exist that assign different encodings to the same character (for fixed frequencies), but the length of this encoding, for each character, will be the same in all codes. #card
?

1. File length with **fixed-length** code: $3 \cdot 70000 = 210000$ ($\lceil \log_2 5 \rceil=3$ bits is the minimum length necessary for encoding 5 characters with a fixed-length code);
   With **variable-length**: encoding lengths $(d : 1), (e : 2), (b : 3), (c : 4), (a : 4)$;
   number of occurrences of characters: $d : 70000 \cdot \frac{53}{100} = 700 \cdot 53 = 37100$; $e : 70000 \cdot \frac{23}{100} = 700 \cdot 23 = 16100$; $b : 70000 \cdot \frac{9}{100} = 700 \cdot 9 = 6300$; $c : 70000 \cdot \frac{8}{100} = 700 \cdot 8 = 5600$; $a : 70000 \cdot \frac{7}{100} = 700 \cdot 7 = 4900$.
   Length of the file compressed with Huffman:

$$

130200 = 1 \cdot 37100 + 2 \cdot 16100 + 3 \cdot 6300 + 4 \cdot 5600 + 4 \cdot 4900.

$$

Absolute saving: $(210000 - 130200)$.
Percentage saving:

$$

\frac{210000 - 130200}{210000} \cdot 100 = 38\%.

$$

📌 Remark:
To easily carry out the calculations by hand, one can proceed as follows:
Length of file compressed with Huffman code:

$$

\begin{aligned}
& 70000 \cdot \frac{53}{100} \cdot 1 + 70000 \cdot \frac{23}{100} \cdot 2 + 70000 \cdot \frac{9}{100} \cdot 3 + 70000 \cdot \frac{8}{100} \cdot 4 + 70000 \cdot \frac{7}{100} \cdot 4 \\
={}& 70000 \cdot \frac{53 + 46 + 27 + 32 + 28}{100} \\
={}& 700 \cdot 186
\end{aligned}

$$

Percentage saving

$$

\frac{700 \cdot 300 - 700 \cdot 186}{700 \cdot 300} \cdot 100 = \left( 1 - \frac{186}{300} \right) \cdot 100 = (1 - 0.62) \cdot 100 = 38.

$$

2. File length with fixed-length code: $180000$;
   encoding lengths $(c : 1), (a : 2), (e : 3), (b : 4), (d : 4)$;
   length of file compressed with Huffman: $101400$.
   Absolute saving: $(180000 - 101400)$.
   Percentage saving:

$$

\frac{180000 - 101400}{180000} \cdot 100 = 43.6666666667 \to 44\%.

$$

Performing calculations using the second method, we have that the length of the file with the Huffman code is $1800 \cdot 169$ and the percentage saving is

$$

\frac{600 \cdot 300 - 600 \cdot 169}{600 \cdot 300} \cdot 100 = \left( 1 - \frac{169}{300} \right) \cdot 100 = (1 - 0.56\overline{3}) \cdot 100 = 43.6666666667 \to 44\%.

$$

The advice is to keep two decimal places in the ratio $\frac{169}{300}$, so as to avoid rounding errors.

3. Percentage saving

$$

\frac{150000 - 114000}{150000} \cdot 100 = 24\%

$$

4. Percentage saving

$$

\frac{90000 - 66900}{90000} \cdot 100 = 25.66\%

$$

5. Percentage saving

$$

\frac{30000 - 22600.0}{30000} = 0.25\%

$$

6. Percentage saving

$$

\frac{180000 - 130800.0}{180000} = 0.27\%

$$
