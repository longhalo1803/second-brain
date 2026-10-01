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
updated: 2026-09-30
difficulty: fundamental
sources:
  - "[[CLRS - Introduction to Algorithms]]"
cross_domain: []
---

# 🧭 DSA Master Vault - Cấu Trúc Dữ Liệu & Giải Thuật

> Kho lưu trữ tri thức chuyên sâu về **Cấu trúc Dữ liệu, Giải thuật, Algorithmic Patterns & Tư duy Thiết kế Hệ thống**. Tối ưu hóa theo **Mô hình Tri thức 3 Tầng (3-Tier Knowledge Architecture)** và phương pháp ôn tập ngắt quãng (Spaced Repetition).
>
> 📌 _Quy định chung về Frontmatter, cấu trúc Note 5 phần và quy trình nạp tri thức tuân thủ theo: [Universal Specification](../README.md#📐-5-quy-định-chung-khi-nạp-tri-thức-universal-specification)._

---

## 🎯 1. Triết Lý Thiết Kế Cốt Lõi (Core Philosophy)

Toàn bộ Vault tuân thủ 3 nguyên tắc tư duy bất di bất dịch:

1. **Mental Model First (Mô hình tư duy trực quan):** Mọi khái niệm đều phải được hình tượng hóa bằng các ví dụ đời thực sinh động (ví dụ: _xé đôi từ điển_ cho Binary Search, _buổi tiệc speed dating_ cho $O(n^2)$, _chiếc hộp thứ 3_ cho Trade-off RAM vs Tốc độ).
2. **Trade-offs Oriented (Lăng kính đánh đổi):** Không có cấu trúc dữ liệu nào "hoàn hảo", chỉ có cấu trúc dữ liệu "phù hợp nhất". Luôn đặt lên bàn cân: _Thời gian vs Bộ nhớ (Time vs Space)_, _Đọc nhanh vs Ghi nhanh (Read vs Write)_, _Chính xác tuyệt đối vs Tiết kiệm RAM (Exact vs Probabilistic)_.
3. **Cross-Domain Systems View (Lăng kính Đa miền Hệ thống):** Cấu trúc dữ liệu không nằm trên giấy mà là nền móng vận hành của các hệ thống thực tế:
   - [[LRU Cache]] $\to$ [[Database-knowledge/01 - Core Concepts/Buffer Cache|Buffer Cache trong Database]] & Linux Virtual Memory Page Replacement.
   - [[Hash Table & HashSet]] $\to$ Hash Index & Hash Join trong SQL Query Optimizer.
   - [[Sliding Window Pattern]] $\to$ TCP Flow Control & Rate Limiting Algorithms trong Backend.

---

## 🏛️ 2. Mô Hình Tri Thức 3 Tầng (3-Tier Architecture)

```
[Tier 1: Primary Sources]  -->  [Tier 2: Atomic DSA Notes]  -->  [Tier 3: Maps of Content & Graphs]
Sources/CLRS.md                 Linear/Array & Dynamic Array.md   00 - Meta & Maps/Master MOC.md
Sources/NeetCode.md             Specialized/LRU Cache.md          00 - Master Dashboard.md
                                Patterns/Sliding Window.md        00 - Master Knowledge Hub.md
```

1. **Tier 1 (Nguồn bất biến - Primary Sources):** Nằm tại thư mục `Sources/` ở gốc Vault (ví dụ: [[CLRS - Introduction to Algorithms]], [[NeetCode - Algorithmic Patterns]]), đảm bảo 100% định nghĩa toán học và công thức tiệm cận không bị ảo giác AI.
2. **Tier 2 (Ghi chú nguyên tử - Atomic Notes):** Mỗi note giải quyết trọn vẹn 1 cấu trúc, 1 thuật toán hoặc 1 pattern kèm Mental Model, Bảng Big-O, Trade-offs và liên kết 2 chiều.
3. **Tier 3 (Bản đồ điều hướng - Maps of Content):** [[Master MOC]] tổng hợp và kết nối các nhánh tri thức, tích hợp đồ thị liên kết chéo sang Database, Backend, và DevOps.

---

## 📂 3. Lộ Trình 6 Giai Đoạn & Cấu Trúc Thư Mục

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
├── 05 - Flashcards/                           # Hơn 200+ Thẻ nhớ Spaced Repetition (#card)
├── 06 - System Applications/                  # Ứng dụng thực tế & Ma trận quyết định kỹ thuật
├── Templates/                                 # Mẫu Note chuẩn hóa cho Templater
└── 99 - Attachments/                          # Hình ảnh & Sơ đồ trực quan
```

---

## 🏷️ 4. Metadata Chuẩn Hóa Cho DSA Notes

Mọi note trong DSA Vault đều mang YAML Frontmatter chuẩn với các trường nguồn và liên kết đa miền:

```yaml
---
title: Tên Cấu trúc / Thuật toán / Pattern
aliases:
  - Tên tiếng Anh (Binary Search, Bloom Filter, Monotonic Stack)
  - Viết tắt (BST, DSU, LRU, O(n log n))
tags:
  - dsa
  - sub-topic # data-structure | algorithm | pattern | mental-model
stage: 1 # Giai đoạn từ 1 đến 6
type: concept # concept | principle | practical | pattern | architecture | moc
difficulty: fundamental # fundamental | intermediate | advanced
status: completed # completed | in-progress | review-needed
sources:
  - "[[CLRS - Introduction to Algorithms]]"
cross_domain:
  - "[[Database-knowledge/01 - Core Concepts/Buffer Cache]]"
created: YYYY-MM-DD
updated: YYYY-MM-DD
---
```

---

## 🔌 5. Hệ Thống Templates & Spaced Repetition

- `Template - Data Structure.md`: Cấu trúc dữ liệu kèm Memory Layout, Bảng Big-O, Trade-offs và Cross-Domain Systems.
- `Template - Algorithm.md`: Thuật toán với chứng minh tính đúng đắn, Big-O và cài đặt chuẩn.
- `Template - Algorithmic Pattern.md`: Khuôn mẫu code chuẩn và danh sách bài tập LeetCode.

### Ôn tập Spaced Repetition Flashcards (`#card`):

```markdown
## 🧠 Thẻ Ghi Nhớ Nhanh (Spaced Repetition)

Điểm yếu chí mạng của Binary Search Tree không tự cân bằng là gì? #card
?
Khi chèn mảng đã sắp xếp, cây bị thoái hóa thành Linked List với chiều cao O(N), làm tốc độ tìm kiếm giảm từ O(log N) xuống O(N).
```

---

## 🚀 6. Điểm Khởi Đầu Tra Cứu

1. 🧭 **[[00 - Master Dashboard]]**: Xem bảng Dashboard Dataview tự động thống kê tiến độ học và phân loại Big-O.
2. 🗺️ **[[Master MOC]]**: Khám phá bản đồ toàn bộ các chuyên đề DSA và liên kết đa miền.
3. 📋 **[[Roadmap]]**: Theo dõi lộ trình 6 giai đoạn từ cơ bản đến nâng cao.
