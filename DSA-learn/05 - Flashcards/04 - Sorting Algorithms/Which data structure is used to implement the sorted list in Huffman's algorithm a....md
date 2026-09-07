---
title: "Which data structure is used to implement the sorted list in Huffman's algorithm a..."
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
  - "Which data structure is used to implement the sorted list in Huffman's algorithm a..."
---

# 🎴 Which data structure is used to implement the sorted list in Huffman's algorithm a...

> [[00 - Flashcards MOC|🎴 Master MOC]] / [[00 - Sorting Algorithms MOC|📁 Sorting Algorithms MOC]]

---

### Q: Which data structure is used to implement the sorted list in Huffman's algorithm and how are its elements defined? #card

?
The data structure used to manage the sorted list in Huffman's algorithm is the **priority queue **(Min-Heap) with the following structure:
**`(el, pr)`**
• Element **`el`:** pointer to the node (or subtree) of the coding tree.
• Priority **`pr`:** the sum of the frequencies of all characters contained in the subtree rooted at that node.

📌 Note: the Priority Queue guarantees efficient extraction of the two minimum-frequency nodes in logarithmic time.
