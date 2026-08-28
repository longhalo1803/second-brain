---
tags:
  - meta
  - dsa
  - moc
type: moc
status: completed
created: 2026-08-27
updated: 2026-08-27
aliases:
  - Master MOC
  - Bản đồ kiến thức DSA
---

# 🗺️ Master MOC - Bản Đồ Tri Thức Cấu Trúc Dữ Liệu & Giải Thuật

> [[00 - Master Dashboard|⬅️ Quay lại Dashboard]] | [[Roadmap|📋 Lộ trình DSA chi tiết]]

---

## 🏛️ Trụ Cột 1: Tư Duy & Độ Phức Tạp (Mental Models & Big-O)
*Nền tảng đo lường hiệu suất và cách bẻ gãy bài toán.*
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

## 📦 Trụ Cột 2: Cấu Trúc Dữ Liệu (Data Structures)

### 1. Tuyến tính (Linear) - Giai đoạn 2
- [[Array & Dynamic Array|Mảng tĩnh & Mảng động (Arrays / Dynamic Arrays)]]: Truy xuất ngẫu nhiên $O(1)$, chèn/xóa $O(n)$.
- [[Linked List|Danh sách liên kết (Singly & Doubly Linked Lists)]]: Chèn/xóa tại con trỏ $O(1)$, tìm kiếm $O(n)$.
- [[Stack|Ngăn xếp (Stack - LIFO)]]: Undo/Redo, Call stack, Monotonic Stack.
- [[Queue & Deque|Hàng đợi (Queue - FIFO) & Hàng đợi 2 đầu (Deque)]]: Xử lý tác vụ, Buffer, Sliding Window.

### 2. Phân Cấp & Tối Ưu Tìm Kiếm (Trees & Hash) - Giai đoạn 4
- [[Hash Table & HashSet|Bảng băm & Tập hợp băm (Hash Table / HashSet)]]: Truy xuất trung bình $O(1)$, đánh đổi bộ nhớ.
- [[Binary Search Tree (BST)|Cây tìm kiếm nhị phân (Binary Search Tree)]]: Tổ chức có thứ tự, $O(\log n)$ khi cân bằng.
- [[Trie (Prefix Tree)|Cây tiền tố (Trie)]]: Tối ưu tìm kiếm từ khóa, Autocomplete.
- [[Binary Heap & Priority Queue|Cây vun đống & Hàng đợi ưu tiên (Heap / Priority Queue)]]: Trích xuất phần tử cực đại/cực tiểu $O(1)$, duy trì $O(\log n)$.

### 3. Mạng Lưới & Đồ Thị (Graphs) - Giai đoạn 6
- [[Graph Representations & Traversal|Đồ thị (Graphs)]]: Biểu diễn Ma trận kề / Danh sách kề, duyệt BFS & DFS.
- `[[Disjoint Set Union (DSU)]]`: Quản lý tập hợp rời rạc, kiểm tra chu trình và liên thông.

### 4. Cấu Trúc Hệ Thống Nâng Cao (System Architect DS) - Giai đoạn 6
- [[LRU Cache|Bộ nhớ đệm LRU (LRU Cache)]]: Kết hợp Hash Table + Doubly Linked List cho $O(1)$ mọi thao tác.
- [[Bloom Filter|Bộ lọc Bloom (Bloom Filter)]]: Cấu trúc xác suất tiết kiệm RAM cực đại.

---

## ⚙️ Trụ Cột 3: Thuật Toán Cốt Lõi (Core Algorithms) - Giai đoạn 3 & 5

### 1. Tìm Kiếm (Searching)
- [[Linear Search|Tìm kiếm tuyến tính (Linear Search)]] ($O(n)$)
- [[Binary Search|Tìm kiếm nhị phân (Binary Search)]] ($O(\log n)$) - *Yêu cầu dữ liệu đã sắp xếp*

### 2. Sắp Xếp (Sorting)
- **Cơ sở ($O(n^2)$):** `[[Bubble Sort]]`, `[[Selection Sort]]`, `[[Insertion Sort]]`
- **Tối ưu ($O(n \log n)$ - Divide & Conquer):**
  - [[Merge Sort|Sắp xếp Trộn (Merge Sort)]]: Luôn ổn định $O(n \log n)$, tốn $O(n)$ bộ nhớ phụ.
  - [[Quick Sort|Sắp xếp Nhanh (Quick Sort)]]: Sắp xếp tại chỗ (In-place), trung bình $O(n \log n)$.
  - `[[Heap Sort]]`: Sắp xếp dựa trên Heap, $O(n \log n)$ In-place.

### 3. Kỹ Thuật Đệ Quy & Quy Hoạch Động
- [[Recursion & Memoization|Đệ quy (Recursion) & Ghi nhớ (Memoization)]]: Base case, Call stack, tối ưu đệ quy trùng lặp.

---

## 🎯 Trụ Cột 4: Mẫu Thuật Toán Thực Chiến (Algorithmic Patterns) - Giai đoạn 5
*Các khuôn mẫu tư duy giúp hạ độ phức tạp từ $O(n^2) \to O(n)$.*

- [[Two Pointers Pattern|Kỹ thuật Hai con trỏ (Two Pointers)]]: Đối đầu hoặc Cùng chiều (Fast/Slow Pointers).
- [[Sliding Window Pattern|Kỹ thuật Cửa sổ trượt (Sliding Window)]]: Xử lý bài toán mảng con / chuỗi con liên tiếp.
- `[[Monotonic Stack Pattern]]`: Tìm phần tử lớn/nhỏ hơn gần nhất trong $O(n)$.
- `[[Top K Elements (Heap Pattern)]]`: Tìm K phần tử lớn nhất/nhỏ nhất mà không cần sort toàn bộ.
- `[[Graph BFS / DFS Patterns]]`: Tìm đường đi ngắn nhất, đếm vùng liên thông.

---

## 🏛️ Trụ Cột 5: Ứng Dụng Thiết Kế Hệ Thống (System Architecture)
- [[Trade-offs & System Architecture Decisions|Ma trận đánh đổi: Bộ nhớ vs Tốc độ, Read vs Write]]
- Ứng dụng: Database Indexing (B-Tree/LSM), Routing Navigation, Distributed Caching.
