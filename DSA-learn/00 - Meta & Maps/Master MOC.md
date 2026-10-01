---
title: Master MOC - Bản Đồ Tri Thức Cấu Trúc Dữ Liệu & Giải Thuật
aliases:
  - Master MOC
  - Bản đồ kiến thức DSA
  - DSA MOC
tags:
  - meta
  - dsa
  - moc
type: moc
difficulty: intermediate
status: completed
sources:
  - "[[CLRS - Introduction to Algorithms]]"
  - "[[NeetCode - Algorithmic Patterns]]"
created: 2026-08-27
updated: 2026-09-30
---

# 🗺️ Master MOC - Bản Đồ Tri Thức Cấu Trúc Dữ Liệu & Giải Thuật

> [[00 - Master Dashboard|⬅️ Quay lại Dashboard]] | [[Roadmap|📋 Lộ trình DSA chi tiết]] | [[00 - Master Knowledge Hub|🌐 Master Vault Hub]]

---

## 📚 1. Tài Liệu Nguồn Cốt Lõi (Tier 1 - Primary Sources)

_Mọi khái niệm, định lý và phân tích tiệm cận trong module này đều bắt nguồn từ các tài liệu nguồn thẩm quyền cao nhất:_

- 📖 [[CLRS - Introduction to Algorithms|CLRS (Introduction to Algorithms 4th Edition - MIT Press)]]: Nguồn gốc toán học về Asymptotic Notation, Recurrences, Sorting, Dynamic Programming và Graph Algorithms.
- 📖 [[NeetCode - Algorithmic Patterns|NeetCode (Algorithmic Patterns & Problem Solving Taxonomy)]]: Phân loại 14+ mẫu thuật toán thực chiến giải quyết bài toán tối ưu từ $O(n^2) \to O(n)$.

---

## 🏛️ 2. Trụ Cột 1: Tư Duy & Độ Phức Tạp (Mental Models & Big-O)

_Nền tảng đo lường hiệu suất và cách bẻ gãy bài toán._

- 🧠 **Tư duy nền tảng:** [[Algorithmic Thinking|Tư duy thuật toán (Algorithmic Thinking)]]
- ⚡ **Thước đo tổng hợp:** [[Big-O Notation - MOC|Big-O Notation MOC]]
  - [[Time Complexity|Độ phức tạp Thời gian (Time Complexity)]]
  - [[Space Complexity|Độ phức tạp Không gian (Space Complexity)]]
  - ⚖️ **Sự đánh đổi cốt lõi:** [[Time Complexity#3. Trade-off (Sự Đánh Đổi) giữa Time Complexity và Space Complexity|Trade-off: Đánh đổi RAM lấy Tốc độ]]
- 📈 **Các cấp độ Big-O:**
  - [[O(1) - Constant Time]]
  - [[O(log n) - Logarithmic Time]]
  - [[O(n) - Linear Time]]
  - [[O(n log n) - Linearithmic Time]]
  - [[O(n^2) - Quadratic Time]]
  - [[O(2^n) - Exponential Time]]
  - [[O(n!) - Factorial Time]]

---

## 📦 3. Trụ Cột 2: Cấu Trúc Dữ Liệu (Data Structures)

### 3.1. Tuyến tính (Linear) - Giai đoạn 2

- [[Array & Dynamic Array|Mảng tĩnh & Mảng động (Arrays / Dynamic Arrays)]]: Truy xuất ngẫu nhiên $O(1)$, chèn/xóa $O(n)$.
- [[Linked List|Danh sách liên kết (Singly & Doubly Linked Lists)]]: Chèn/xóa tại con trỏ $O(1)$, tìm kiếm $O(n)$.
- [[Stack|Ngăn xếp (Stack - LIFO)]]: Undo/Redo, Call stack, Monotonic Stack.
- [[Queue & Deque|Hàng đợi (Queue - FIFO) & Hàng đợi 2 đầu (Deque)]]: Xử lý tác vụ, Buffer, Sliding Window.

### 3.2. Phân Cấp & Tối Ưu Tìm Kiếm (Trees & Hash) - Giai đoạn 4

- [[Hash Table & HashSet|Bảng băm & Tập hợp băm (Hash Table / HashSet)]]: Truy xuất trung bình $O(1)$, đánh đổi bộ nhớ.
- [[Binary Search Tree (BST)|Cây tìm kiếm nhị phân (Binary Search Tree)]]: Tổ chức có thứ tự, $O(\log n)$ khi cân bằng.
- [[Trie (Prefix Tree)|Cây tiền tố (Trie)]]: Tối ưu tìm kiếm từ khóa, Autocomplete.
- [[Binary Heap & Priority Queue|Cây vun đống & Hàng đợi ưu tiên (Heap / Priority Queue)]]: Trích xuất phần tử cực đại/cực tiểu $O(1)$, duy trì $O(\log n)$.

### 3.3. Mạng Lưới & Đồ Thị (Graphs) - Giai đoạn 6

- [[Graph Representations & Traversal|Đồ thị (Graphs)]]: Biểu diễn Ma trận kề / Danh sách kề, duyệt BFS & DFS.
- [[Disjoint Set Union (DSU)|Tập hợp rời rạc (DSU - Union-Find)]]: Quản lý tập hợp rời rạc, kiểm tra chu trình và liên thông trong $O(\alpha(n))$.

### 3.4. Cấu Trúc Hệ Thống Nâng Cao (System Architect DS) - Giai đoạn 6

- [[LRU Cache|Bộ nhớ đệm LRU (LRU Cache)]]: Kết hợp Hash Table + Doubly Linked List cho $O(1)$ mọi thao tác.
- [[Bloom Filter|Bộ lọc Bloom (Bloom Filter)]]: Cấu trúc xác suất tiết kiệm RAM cực đại.

---

## ⚙️ 4. Trụ Cột 3: Thuật Toán Cốt Lõi (Core Algorithms) - Giai đoạn 3 & 5

### 4.1. Tìm Kiếm (Searching)

- [[Linear Search|Tìm kiếm tuyến tính (Linear Search)]] ($O(n)$)
- [[Binary Search|Tìm kiếm nhị phân (Binary Search)]] ($O(\log n)$) - _Yêu cầu dữ liệu đã sắp xếp_

### 4.2. Sắp Xếp (Sorting)

- **Cơ sở ($O(n^2)$):** [[Bubble Sort]], [[Selection Sort]], [[Insertion Sort]]
- **Tối ưu ($O(n \log n)$ - Divide & Conquer):**
  - [[Merge Sort|Sắp xếp Trộn (Merge Sort)]]: Luôn ổn định $O(n \log n)$, tốn $O(n)$ bộ nhớ phụ.
  - [[Quick Sort|Sắp xếp Nhanh (Quick Sort)]]: Sắp xếp tại chỗ (In-place), trung bình $O(n \log n)$.

### 4.3. Kỹ Thuật Đệ Quy & Quy Hoạch Động

- [[Recursion & Memoization|Đệ quy (Recursion) & Ghi nhớ (Memoization)]]: Base case, Call stack, tối ưu đệ quy trùng lặp.
- [[Dynamic Programming|Quy hoạch động toàn diện (Dynamic Programming)]]: Top-Down (Memoization), Bottom-Up (Tabulation), Space Optimization $O(1)$, Unique Paths & 0/1 Knapsack.
- [[Greedy Algorithm|Thuật toán Tham lam (Greedy Algorithm)]]: Lựa chọn tối ưu cục bộ, Greedy Choice Property, Fractional Knapsack, Interval Scheduling.

---

## 🎯 5. Trụ Cột 4: Mẫu Thuật Toán Thực Chiến (Algorithmic Patterns) - Giai đoạn 5

_Các khuôn mẫu tư duy giúp hạ độ phức tạp từ $O(n^2) \to O(n)$._

- [[Two Pointers Pattern|Kỹ thuật Hai con trỏ (Two Pointers)]]: Đối đầu hoặc Cùng chiều (Fast/Slow Pointers).
- [[Sliding Window Pattern|Kỹ thuật Cửa sổ trượt (Sliding Window)]]: Xử lý bài toán mảng con / chuỗi con liên tiếp.
- [[Monotonic Stack Pattern|Kỹ thuật Ngăn xếp đơn điệu (Monotonic Stack)]]: Tìm phần tử lớn/nhỏ hơn gần nhất trong $O(n)$.
- [[Top K Elements Pattern|K phần tử hàng đầu (Top K Elements via Heap)]]: Tìm K phần tử lớn nhất/nhỏ nhất mà không cần sort toàn bộ.

---

## 🌐 6. Liên Kết Đa Miền Hệ Thống (Cross-Domain Graph Integration)

_Cấu trúc dữ liệu và giải thuật không tồn tại cô lập mà là động cơ của Database, Network Protocols và OS Kernel:_

| Cấu trúc DSA                 | Domain liên kết       | Khái niệm & Ứng dụng thực tế                                                                                         |
| :--------------------------- | :-------------------- | :------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------- | --------------------- |
| [[LRU Cache]]                | `Database-knowledge`  | [[Database-knowledge/01 - Core Concepts/Buffer Cache                                                                 | Buffer Cache & Buffer Pool Management]]                             |
| [[Hash Table & HashSet]]     | `Database-knowledge`  | [[Database-knowledge/01 - Core Concepts/Index                                                                        | Hash Index]] & [[Database-knowledge/01 - Core Concepts/Join Methods | Hash Join Algorithm]] |
| [[Binary Search Tree (BST)]] | `Database-knowledge`  | Nền tảng tư duy phân cấp dẫn tới B+Tree: [[Database-knowledge/01 - Core Concepts/Index                               | B+Tree Index]]                                                      |
| [[Sliding Window Pattern]]   | `Backend-full-course` | [[Backend-full-course/Part 1 - Core Foundations/01 - Computer Networks & Protocols/Core Transport & Routing/TCP - IP | TCP Flow Control Sliding Window]]                                   |
| [[Queue & Deque]]            | `Backend-full-course` | Message Queues, Event Loop, Ingress Buffering                                                                        |
| [[Array & Dynamic Array]]    | `DevOps-knowledge`    | CPU Cache Locality (L1/L2/L3), Memory Paging & Linux Virtual File System                                             |

---

## 🎴 7. Hệ Thống Thẻ Nhớ Spaced Repetition (Flashcards)

- [[DSA-learn/05 - Flashcards/00 - Flashcards MOC|🎴 Master Flashcards MOC]]
- [[DSA-learn/05 - Flashcards/01 - Complexity & Fundamentals/00 - Complexity & Fundamentals MOC|📁 Complexity & Fundamentals]]
- [[DSA-learn/05 - Flashcards/02 - Linear Data Structures & Hashing/00 - Linear Data Structures & Hashing MOC|📁 Linear DS & Hashing]]
- [[DSA-learn/05 - Flashcards/03 - Trees & Heaps/00 - Trees & Heaps MOC|📁 Trees & Heaps]]
- [[DSA-learn/05 - Flashcards/04 - Sorting Algorithms/00 - Sorting Algorithms MOC|📁 Sorting Algorithms]]
- [[DSA-learn/05 - Flashcards/05 - Graph Algorithms/00 - Graph Algorithms MOC|📁 Graph Algorithms]]
- [[DSA-learn/05 - Flashcards/06 - Recursion & Dynamic Programming/00 - Recursion & Dynamic Programming MOC|📁 Recursion & Dynamic Programming]]
