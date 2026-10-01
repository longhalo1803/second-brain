---
title: "CLRS: Introduction to Algorithms (4th Edition)"
aliases:
  - CLRS
  - Introduction to Algorithms
  - Cormen Leiserson Rivest Stein
tags:
  - source
  - literature
  - dsa
  - algorithms
  - textbook
type: reference
author: Thomas H. Cormen, Charles E. Leiserson, Ronald L. Rivest, Clifford Stein
publisher: MIT Press
edition: 4th Edition (2022)
status: completed
created: 2026-09-30
updated: 2026-09-30
---

# 📖 CLRS: Introduction to Algorithms (4th Edition)

> **Tài liệu nguồn bất biến (Tier 1 - Primary Source)** cho toàn bộ hệ thống tri thức DSA trong Vault.
> Mọi định nghĩa tiệm cận ($O, \Omega, \Theta$), công thức truy hồi và phân tích tiệm cận trong `DSA-learn` đều bắt nguồn từ cuốn sách này.

---

## 📑 1. Cấu Trúc Khối Tri Thức Cốt Lõi (Key Parts & Chapters)

### Phần I: Nền Tảng & Tiệm Cận (Foundations)

- **Chương 3 - Asymptotic Notation:** Định nghĩa toán học chặt chẽ về $O(g(n))$, $\Omega(g(n))$, $\Theta(g(n))$, $o(g(n))$, $\omega(g(n))$.
  - Định lý: $f(n) = \Theta(g(n)) \iff f(n) = O(g(n)) \land f(n) = \Omega(g(n))$.
- **Chương 4 - Divide-and-Conquer & Recurrences:**
  - Phương pháp thế (Substitution Method).
  - Cây đệ quy (Recursion-tree Method).
  - Định lý Thợ (Master Theorem) cho dạng $T(n) = aT(n/b) + f(n)$.

### Phần II: Sắp Xếp & Thống Kê Thứ Tự (Sorting & Order Statistics)

- **Chương 6 - Heapsort:** Cấu trúc Max-Heap, Min-Heap, duy trì tính chất Heap trong $O(\log n)$, xây dựng Heap trong $O(n)$.
- **Chương 7 - Quicksort:** Thuật toán phân hoạch Lomuto & Hoare, độ phức tạp trung bình $\Theta(n \log n)$, trường hợp xấu nhất $O(n^2)$.
- **Chương 8 - Sorting in Linear Time:** Giới hạn dưới của so sánh $\Omega(n \log n)$; Counting Sort, Radix Sort, Bucket Sort.

### Phần III: Cấu Trúc Dữ Liệu Nền Tảng (Data Structures)

- **Chương 10 - Elementary Data Structures:** Stacks, Queues, Doubly Linked Lists.
- **Chương 11 - Hash Tables:** Direct-address tables, Hash functions (Division, Multiplication), Chaining, Open Addressing (Linear Probing, Double Hashing).
- **Chương 12 - Binary Search Trees:** Cây BST, In-order tree walk, Tree-Search, Insert, Delete (Case 3 thay thế bằng successor/predecessor).

### Phần IV: Kỹ Thuật Thiết Kế Nâng Cao (Advanced Design & Analysis)

- **Chương 14 - Dynamic Programming:** 4 bước giải bài toán Quy hoạch động, Optimal Substructure, Overlapping Subproblems (Rod Cutting, Matrix-chain Multiplication, LCS, 0/1 Knapsack).
- **Chương 15 - Greedy Algorithms:** Greedy-choice property, Fractional Knapsack, Huffman Codes.
- **Chương 16 - Amortized Analysis:** Phân tích khấu hao (Aggregate analysis, Accounting method, Potential method) áp dụng cho Mảng động ($2\times$ resizing).

### Phần V: Thuật Toán Đồ Thị (Graph Algorithms)

- **Chương 20 - Elementary Graph Algorithms:** Biểu diễn danh sách kề (Adjacency List) vs Ma trận kề (Adjacency Matrix), BFS (đường đi ngắn nhất trên đồ thị không trọng số), DFS (thời gian khám phá và hoàn thành $d[u], f[u]$, Topological Sort).
- **Chương 21 - Minimum Spanning Trees:** Kruskal (dùng DSU) và Prim (dùng Min-Heap).
- **Chương 22 - Single-Source Shortest Paths:** Dijkstra (trọng số không âm), Bellman-Ford (phát hiện chu trình âm).
- **Chương 23 - All-Pairs Shortest Paths:** Floyd-Warshall ($O(V^3)$ Dynamic Programming).

---

## 🔗 2. Các Atomic Notes Dẫn Xuất (Tier 2 Derived Notes)

Toàn bộ các note sau trong `DSA-learn` đều kế thừa trực tiếp từ nguồn tài liệu này:

- Nền tảng: [[Time Complexity]], [[Space Complexity]], [[O(1) - Constant Time]], [[O(log n) - Logarithmic Time]], [[O(n) - Linear Time]], [[O(n log n) - Linearithmic Time]], [[O(n^2) - Quadratic Time]].
- Cấu trúc dữ liệu: [[Array & Dynamic Array]], [[Linked List]], [[Stack]], [[Queue & Deque]], [[Hash Table & HashSet]], [[Binary Search Tree (BST)]], [[Binary Heap & Priority Queue]], [[Graph Representations & Traversal]], [[Disjoint Set Union (DSU)]].
- Thuật toán: [[Linear Search]], [[Binary Search]], [[Merge Sort]], [[Quick Sort]], [[Bubble Sort]], [[Insertion Sort]], [[Selection Sort]], [[Recursion & Memoization]], [[Dynamic Programming]], [[Greedy Algorithm]].

---

## 🎴 3. Bộ Thẻ Nhớ Spaced Repetition Tương Ứng

Nguồn này đã được trích xuất thành hơn 200 thẻ nhớ flashcard tại:

- [[DSA-learn/05 - Flashcards/01 - Complexity & Fundamentals/00 - Complexity & Fundamentals MOC|Flashcards: Complexity & Fundamentals]]
- [[DSA-learn/05 - Flashcards/02 - Linear Data Structures & Hashing/00 - Linear Data Structures & Hashing MOC|Flashcards: Linear & Hashing]]
- [[DSA-learn/05 - Flashcards/04 - Sorting Algorithms/00 - Sorting Algorithms MOC|Flashcards: Sorting Algorithms]]
- [[DSA-learn/05 - Flashcards/06 - Recursion & Dynamic Programming/00 - Recursion & Dynamic Programming MOC|Flashcards: Recursion & DP]]
