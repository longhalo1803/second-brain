---
tags:
  - dsa
  - pattern
  - heap
stage: 5
type: pattern
status: completed
created: 2026-08-27
updated: 2026-08-27
aliases:
  - Top K Elements
  - Top K Elements Pattern
  - Top K Elements (Heap Pattern)
---

# 🏔️ Mẫu Top K Phần Tử (Top K Elements Pattern)

> [[00 - Master Dashboard|🧭 Dashboard]] / [[Master MOC|🗺️ Master MOC]] / [[Roadmap|📋 Roadmap]]

---

## 1. Bản Chất Cốt Lõi (Mental Model)
- **Mục tiêu:** Tìm $K$ phần tử lớn nhất, nhỏ nhất hoặc có tần suất xuất hiện nhiều nhất trong tập dữ liệu mà không cần phải sắp xếp toàn bộ danh sách ($O(n \log n)$).
- **Vũ khí bí mật:** Sử dụng [[Binary Heap & Priority Queue|Cây vun đống (Heap)]] có kích thước tối đa là $K$:
  - Để tìm **K phần tử lớn nhất:** Dùng một **Min-Heap** kích thước $K$.
  - Để tìm **K phần tử nhỏ nhất:** Dùng một **Max-Heap** kích thước $K$.
- **Độ phức tạp tối ưu:**
  - Thời gian: **$O(n \log K)$** (với $K \ll N$, tốc độ nhanh hơn vượt trội so với $O(n \log n)$).
  - Bộ nhớ (Space): **$O(K)$** — Cực kỳ lý tưởng cho dữ liệu luồng (Data Streams) khổng lồ không thể chứa hết trong RAM.

---

## 2. Các Bài Toán Thực Chiến
- **Kth Largest Element in an Array (LeetCode 215)**
- **Top K Frequent Elements (LeetCode 347)**
- **Find K Closest Points to Origin (LeetCode 973)**
- **Merge K Sorted Lists (LeetCode 23)**
