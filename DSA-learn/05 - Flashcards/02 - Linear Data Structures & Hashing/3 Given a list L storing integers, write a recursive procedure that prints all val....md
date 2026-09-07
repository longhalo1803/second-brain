---
title: "3 Given a list L storing integers, write a recursive procedure that prints all val..."
tags:
  - dsa
  - flashcards
  - clrs
  - data-structures
type: reference
status: completed
created: 2026-09-25
updated: 2026-09-25
aliases:
  - "3 Given a list L storing integers, write a recursive procedure that prints all val..."
---

# 🎴 3 Given a list L storing integers, write a recursive procedure that prints all val...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Linear Data Structures & Hashing MOC|📁 Linear Data Structures & Hashing MOC]]

---

### Q: 📝 3 Given a list $L$ storing integers, write a **recursive** procedure that prints all values stored in the list in the **reverse** order of their appearance. Illustrate the step-by-step execution on an example list. #card

?
The solution differs from that of Exercise 2 by the position of the recursive call relative to printing the value in the node.
To print in reverse order, the print statement is moved _after_ the recursive call.
This way, the print operations occur during the unwinding phase of the call stack.

- **Base case:** Empty list ($\textsf{L} = \textsf{NIL}$), recursion terminates without doing anything.
- **Recursive case:** The recursive call is executed first on the next node ($\textsf{L.next}$), and upon returning from recursion, $\textsf{L.val}$ is printed.

```text
{aligned}                            // PrintListReverse(L)
    // if L ≠q NIL then
        // PrintListReverse(L.next)
        // print L.val {aligned}
```

**Main call:** $\texttt{PrintListReverse}(\textsf{L})$

**📝 **Step-by-step execution (example with list $L = \langle 1, 2, 3, 4, 5 \rangle$):

- **Descent (recursive calls):**
- 1st call with $\textsf{L} \to 1$: invokes $\texttt{PrintListReverse}(\textsf{L.next})$
- 2nd call with $\textsf{L} \to 2$: invokes $\texttt{PrintListReverse}(\textsf{L.next})$
- 3rd call with $\textsf{L} \to 3$: invokes $\texttt{PrintListReverse}(\textsf{L.next})$
- 4th call with $\textsf{L} \to 4$: invokes $\texttt{PrintListReverse}(\textsf{L.next})$
- 5th call with $\textsf{L} \to 5$: invokes $\texttt{PrintListReverse}(\textsf{NIL})$
- 6th call with $\textsf{L} = \textsf{NIL}$: base case reached, returns immediately.
- **Unwinding (printing values):**
- Return to 5th call: executes $\texttt{print } 5$
- Return to 4th call: executes $\texttt{print } 4$
- Return to 3rd call: executes $\texttt{print } 3$
- Return to 2nd call: executes $\texttt{print } 2$
- Return to 1st call: executes $\texttt{print } 1$
  **Final printed output:** $5, 4, 3, 2, 1$

📌 Note: computational cost is $\Theta(n)$ in time and requires $\Theta(n)$ stack frames for the recursion.
