---
title: "How does the Merge Sort algorithm work according to the Divide and Conquer paradig..."
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
  - "How does the Merge Sort algorithm work according to the Divide and Conquer paradig..."
---

# 🎴 How does the Merge Sort algorithm work according to the Divide and Conquer paradig...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: How does the Merge Sort algorithm work according to the _Divide and Conquer_ paradigm, and what is its base case? #card

?
**Merge Sort** is a sorting algorithm based on the **Divide and Conquer** paradigm:

- **DIVIDE:** divide the array of $n$ elements into two balanced sub-sequences of $\textcolor{gray}{k - i + 1 =} \lceil n/2 \rceil$ and $\textcolor{gray}{j - k =} \lfloor n/2 \rfloor$ elements each;
- **CONQUER:** sort the two sub-sequences recursively by calling Merge Sort on each half;
- **COMBINE (Merge):** merge the two already sorted halves into a single sorted sequence.**Base case:**
  The problem is trivial to solve when the sub-sequence contains **a single element** (or is empty) because it is, by definition, already sorted and is directly returned without further recursive calls.

📌 Note: the real sorting logic lies in the combination phase (the `Merge` procedure), which builds the sorted order by merging sorted sub-arrays.
