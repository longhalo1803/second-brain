---
title: Hướng dẫn Sử dụng & Quản trị Kho Tri thức DSA
aliases:
  - README
  - DSA Vault Guide
tags:
  - meta
  - dsa
  - algorithms
  - data-structures
type: reference
created: 2026-08-27
updated: 2026-08-28
---

# 🧭 DSA Master Vault - Cấu Trúc Dữ Liệu & Giải Thuật

> Kho lưu trữ tri thức chuyên sâu về **Cấu trúc Dữ liệu, Giải thuật, Algorithmic Patterns & Tư duy Thiết kế Hệ thống**. Tối ưu hóa cho phương pháp Mental Models và ôn tập ngắt quãng (Spaced Repetition).
> 
> 📌 *Quy định chung về Frontmatter, cấu trúc Note 5 phần và quy trình nạp tri thức tuân thủ theo: [Universal Specification](../README.md#📐-5-quy-định-chung-khi-nạp-tri-thức-universal-specification).*

---

## 🎯 1. Triết Lý Thiết Kế Cốt Lõi (Core Philosophy)

Toàn bộ Vault tuân thủ 3 nguyên tắc tư duy bất di bất dịch:

1. **Mental Model First (Mô hình tư duy trực quan):** Mọi khái niệm đều phải được hình tượng hóa bằng các ví dụ đời thực sinh động (ví dụ: *xé đôi từ điển* cho Binary Search, *buổi tiệc speed dating* cho $O(n^2)$, *chiếc hộp thứ 3* cho Trade-off RAM vs Tốc độ).
2. **Trade-offs Oriented (Lăng kính đánh đổi):** Không có cấu trúc dữ liệu nào "hoàn hảo", chỉ có cấu trúc dữ liệu "phù hợp nhất". Luôn đặt lên bàn cân: *Thời gian vs Bộ nhớ (Time vs Space)*, *Đọc nhanh vs Ghi nhanh (Read vs Write)*, *Chính xác tuyệt đối vs Tiết kiệm RAM (Exact vs Probabilistic)*.
3. **Systems & Patterns View (Góc nhìn Kiến trúc sư):** Nắm vững các "Khuôn mẫu" (Algorithmic Patterns) để biến bài toán phức tạp từ $O(n^2) \to O(n)$, và thấu hiểu cách Big Tech ứng dụng DSA vào Database Indexing, Caching, Routing hay Streaming Data.

---

## 📂 2. Lộ Trình 6 Giai Đoạn & Cấu Trúc Thư Mục

```text
DSA-learn/
├── 00 - Meta & Maps/                          # Trung tâm điều khiển & Quản lý tiến độ
│   ├── 00 - Master Dashboard.md               # 🧭 Dashboard Dataview tra cứu tiến độ & Big-O
│   ├── Master MOC.md                          # 🗺️ Bản đồ liên kết tổng (Map of Content)
│   └── Roadmap.md                             # 📋 Lộ trình 6 giai đoạn học tập chi tiết
│
├── 01 - Mental Models & Complexity/           # Giai đoạn 1: Nền tảng Tư duy & Thước đo Big-O (O(1) -> O(n!))
│
├── 02 - Data Structures/                      # Trụ cột Cấu Trúc Dữ Liệu
│   ├── 01 - Linear/                           # Giai đoạn 2: Tuyến tính (Array, Linked List, Stack, Queue, Deque)
│   ├── 02 - Trees & Hierarchies/              # Giai đoạn 4: Cây & Bảng băm (Hash Table, BST, Trie, Heap)
│   ├── 03 - Graphs & Networks/                # Giai đoạn 6: Đồ thị & Mạng lưới (Graph, BFS/DFS, DSU)
│   └── 04 - Specialized & System/             # Giai đoạn 6: Cấu trúc hệ thống (Bloom Filter, LRU Cache)
│
├── 03 - Algorithms/                           # Trụ cột Thuật Toán Cốt Lõi (Giai đoạn 3 & 5)
│   ├── 01 - Searching/                        # Binary Search, Linear Search
│   ├── 02 - Sorting/                          # Bubble, Selection, Insertion, Merge Sort, Quick Sort
│   └── 03 - Recursion & DP/                   # Đệ quy, Base Case, Memoization (Top-Down DP)
│
├── 04 - Patterns & Techniques/                # Giai đoạn 5: Mẫu Thuật Toán Thực Chiến (Two Pointers, Sliding Window, Monotonic Stack...)
├── 05 - Problem Solving/                      # Ghi chép lời giải & phân tích bài tập LeetCode
├── 06 - System Applications/                  # Ứng dụng thực tế & Ma trận quyết định kỹ thuật
├── Templates/                                 # 4 Mẫu Note chuẩn hóa cho Templater
└── Excalidraw/                                # Lưu trữ sơ đồ Mindmap & Hình vẽ trực quan
```

---

## 🏷️ 3. Metadata Đặc Thù Cho DSA Vault

Khi nạp note mới vào DSA Vault, bổ sung các trường phân loại theo giai đoạn (stage) và loại thuật toán trong Frontmatter:

```yaml
---
title: Tên Cấu trúc / Thuật toán / Pattern
aliases:
  - Tên tiếng Anh (ví dụ: Binary Search, Bloom Filter, Monotonic Stack)
  - Viết tắt (BST, DSU, LRU, O(n log n))
tags:
  - dsa
  - sub-topic # data-structure | algorithm | pattern | leetcode | mental-model
stage: 1 # Giai đoạn từ 1 đến 6
type: data-structure # data-structure | algorithm | pattern | problem | mental-model | moc
status: in-progress # completed | in-progress | review-needed
created: YYYY-MM-DD
updated: YYYY-MM-DD
---
```

---

## 🔌 4. Hệ Thống 4 Templates & Plugin Hỗ Trợ

Vault đã được tích hợp sẵn 4 Template chuẩn trong thư mục `Templates/`:
- `Template - Data Structure.md` : Dành cho Cấu trúc dữ liệu (Mental model, Bảng Big-O, Trade-offs, Mã nguồn).
- `Template - Algorithm.md` : Dành cho Thuật toán.
- `Template - Algorithmic Pattern.md` : Dành cho Mẫu thuật toán thực chiến.
- `Template - LeetCode Problem.md` : Dành cho phân tích bài tập LeetCode.

### Ôn tập Spaced Repetition Flashcards (`#card`):
Ở cuối mỗi bài học, tạo 2-3 câu hỏi bản chất kèm thẻ `#card` để hệ thống Spaced Repetition tự động nhắc nhở ôn tập hàng ngày:
```markdown
## 🧠 Thẻ Ghi Nhớ Nhanh (Spaced Repetition)
Điểm yếu chí mạng của Binary Search Tree không tự cân bằng là gì? #card
?
- Khi chèn mảng đã sắp xếp, cây bị thoái hóa thành Linked List với chiều cao O(N), làm tốc độ tìm kiếm giảm từ O(log N) xuống O(N).
```

---

## 🚀 5. Điểm Khởi Đầu Tra Cứu

1. 🧭 **[[00 - Master Dashboard]]**: Xem bảng Dashboard Dataview tự động thống kê tiến độ học và phân loại Big-O.
2. 🗺️ **[[Master MOC]]**: Khám phá bản đồ toàn bộ các chuyên đề DSA.
3. 📋 **[[Roadmap]]**: Theo dõi lộ trình 6 giai đoạn từ cơ bản đến nâng cao.
