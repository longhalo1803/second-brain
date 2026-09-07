---
title: "Exercise 2.6"
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
  - "Exercise 2.6"
---

# 🎴 Exercise 2.6

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Recursion & Dynamic Programming MOC|📁 Recursion & Dynamic Programming MOC]]

---

### Q: 📝📍 **Exercise 2.6**

Given the recurrence equation:

$$

T(n) = \begin{cases} 1 & \text{if } n \le 1 \\ 3T(n/\alpha) + n^{2.5} & \text{if } n > 1 \end{cases}

$$

State whether, and if so for which values of the real parameter $\alpha \ge 0$, it is possible that $T(n) = O(n^{2.5} \log n)$ using the **Master Theorem**. #card
?
Using the Master Theorem it turns out that the answer is **affirmative** provided that it satisfies the second condition, namely $\log_{\alpha} 3 = 2.5$, from which we get $\alpha = 3^{1/2.5}$.

**Steps:**

1. Identification of parameters:

```text
T(n) = 3T(n/) + n^{2.5} a = 3, b = , d = 2.5 = {25}{10} = {5}{2}
```

2. Case 2 condition of the Master Theorem for $T(n) = \Theta(n^{2.5} \log n)$:

$$

\log*b a = d \implies \log*\alpha 3 = 2.5

$$

3. Algebraic solving for $\alpha$ (many equivalent ways to write the same result):

$$

\begin{aligned}
\log\_\alpha 3 = 2.5 &\iff \alpha^{2.5} = 3 \;\small{\text{ or }}\; \alpha^{5/2} = 3 \\
&\iff \alpha = 3^{\frac{1}{2.5}} = 3^{\frac{2}{5}} \;\small{\text{ or }}\; (\alpha^{5/2})^2 = 3^2 \\
&\iff \alpha = (3^2)^{\frac{1}{5}} \;\small{\text{ or }}\; \alpha^5 = 9 \\
&\iff \alpha = 9^{1/5} \;\small{\text{ or }}\; \alpha = \sqrt[5]{9}
\end{aligned}

$$

Therefore $\alpha = 3^{1/2.5} = 3^{2/5} = \sqrt[5]{9} = 9^{1/5}$.
