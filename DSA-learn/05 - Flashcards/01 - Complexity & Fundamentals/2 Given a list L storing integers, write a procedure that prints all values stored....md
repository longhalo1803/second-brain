---
title: "2 Given a list L storing integers, write a procedure that prints all values stored..."
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
  - "2 Given a list L storing integers, write a procedure that prints all values stored..."
---

# 🎴 2 Given a list L storing integers, write a procedure that prints all values stored...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Complexity & Fundamentals MOC|📁 Complexity & Fundamentals MOC]]

---

### Q: 📝 2 Given a list $L$ storing integers, write a procedure that prints all values stored in the list in the order they appear. Provide both the iterative and recursive versions. #card

?
**1. Recursive version:**
Leverages the recursive nature of the list, viewed as a node ($\textsf{head}$) followed by a sublist ($\textsf{tail} = \textsf{L.next}$).

- **Base case:** The list is empty ($\textsf{L} = \textsf{NIL}$). No operation is performed.
- **Recursive case:** The list is not empty. The value stored in the current node ($\textsf{L.val}$) is printed and the procedure is recursively called on the sublist ($\textsf{L.next}$).

```text
{aligned}                            // PrintListR(L)
    // if L ≠q NIL then
        // print L.val
        // PrintListR(L.next) {aligned}
```

**Main call:** $\texttt{PrintListR}(\textsf{L})$

**2. Iterative version:**
Traverse the list node by node starting from the first one ($\textsf{L}$) and advancing through the $\textsf{next}$ field until reaching $\textsf{NIL}$.

```text
{aligned}                            // PrintListI(L)
    // while L ≠q NIL do
        // print L.val
        // L := L.next {aligned}
```

📌 Note: both versions visit each node exactly once, with a computational cost of $\Theta(n)$, where $n$ is the number of nodes in the list.
