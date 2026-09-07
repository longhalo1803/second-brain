---
title: "What is the formula to calculate how many terms a summation has (or how many itera..."
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
  - "What is the formula to calculate how many terms a summation has (or how many itera..."
---

# 🎴 What is the formula to calculate how many terms a summation has (or how many itera...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Complexity & Fundamentals MOC|📁 Complexity & Fundamentals MOC]]

---

### Q: What is the formula to calculate **how many terms a summation has** (or **how many iterations a `for` loop performs**) in an interval from $i = a$ to $i = b$ _inclusive of endpoints_ (and with a step size of 1)?

And what if the step is not 1 but a generic step $k$?

$$
\sum_{i=a}^{b} \dots
$$

`for i = a to b ...
` `for i = a to b **step 2** ...` #card
?
The formula (end bound - start bound + 1) holds, i.e., given the summation $\sum_{i=a}^{b} \dots$

$$
\text{number of terms} = \boxed{b - a + 1}
$$

📝 Example:
`for i = 2 to 30
    sum = sum + 1`
$\sum_{i=2}^{30} 1$
Number of terms summed/iterations: $30 - 2 + 1 = 29$.
Each term is equal to 1 and the index increment is 1, so the final sum is $29$. In general $\sum_{i=a}^{b} c = c \cdot (\text{number of terms})$.

📌 Note: for step $k > 1$:

$$
\text{number of terms} = \boxed{\left\lfloor \frac{b - a}{k} \right\rfloor + 1}
$$

📝 Example (step 3):
`for i = 2 to 30 step 3:
``    sum += 1`

$$
\sum_{i=2}^{30,\, i+=3} 1
$$

$$
\text{number of terms} = \frac{30 - 2}{3} = 9.33 \implies \lfloor 9.33 \rfloor + 1 = 10
$$
