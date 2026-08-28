---
title: Các Thuật toán Join trong Database (Join Methods)
aliases:
  - Join Methods
  - Join Method
  - Thuật toán Join
  - Nested Loop Join
  - Hash Join
  - Merge Join
  - Sort Merge Join
tags:
  - database
  - sql-tuning
  - optimizer
  - performance
  - core-concept
type: concept
created: 2026-08-26
updated: 2026-08-26
---

# 🔗 Các Thuật toán Kết hợp Bảng (Join Methods)

⬅️ **[[MOC - Query Optimization]]** | 🔗 **[[MOC - Database Overview]]**

---

## 1. Tổng quan

Khi một câu lệnh SQL thực hiện kết nối từ 2 bảng trở lên (`JOIN`), **[[SQL Optimizer]]** phải quyết định sử dụng 1 trong 3 thuật toán nền tảng:

| Thuật toán | Cơ chế Hoạt động | Phù hợp nhất khi | Độ phức tạp |
| :--- | :--- | :--- | :--- |
| **[[Nested Loop Join]]** | Chạy 2 vòng lặp `for` lồng nhau | 1 bảng nhỏ (Outer) + Bảng lớn có Index (Inner) | $O(N 	imes \log M)$ |
| **[[Hash Join]]** | Tạo Hash Table trên RAM cho bảng nhỏ, sau đó quét bảng lớn để đối chiếu | 2 tập dữ liệu lớn, phép nối bằng (`=`), không có Index | $O(N + M)$ |
| **[[Merge Join]]** | Sắp xếp 2 bảng theo khóa Join rồi quét song song ghép cặp | 2 tập dữ liệu đã được sắp xếp sẵn hoặc có toán tử so sánh (`<, >`) | $O(N \log N + M \log M)$ |

---

## 2. Chi tiết & Phân tích Chuyên sâu

### 2.1. Nested Loop Join
```python
# Mô phỏng thuật toán Nested Loop
for outer_row in outer_table: # Driving Table (Bảng dẫn đầu)
    # Tìm kiếm nhanh qua B-Tree Index của Inner Table
    for inner_row in index_lookup(inner_table, outer_row.join_key):
        yield combine(outer_row, inner_row)
```
- **Điểm mạnh:** Trả về những dòng đầu tiên cực nhanh (Fast First Rows), tốn rất ít bộ nhớ RAM.
- **Điểm chết người:** Nếu bảng ngoài (Driving table) có hàng triệu dòng thay vì vài chục dòng, vòng lặp triệu lần sẽ làm hệ thống bị treo đơ ngay lập tức (Xem: **[[Case - Hai bảng giống nhau nhưng hiệu năng khác nhau]]**).

### 2.2. Hash Join
```python
# Mô phỏng thuật toán Hash Join
hash_table = {}
# Giai đoạn 1: Build Phase
for row in build_table:
    hash_table[hash(row.key)].append(row)

# Giai đoạn 2: Probe Phase
for row in probe_table:
    if hash(row.key) in hash_table:
        yield combine(hash_table[hash(row.key)], row)
```
- **Điểm mạnh:** Cực kỳ mạnh mẽ cho các câu truy vấn phân tích (OLAP/Data Warehouse) trên hàng triệu bản ghi.
- **Yêu cầu:** Cần đủ bộ nhớ RAM (PGA / TempDB) để chứa Hash Table. Nếu thiếu RAM, dữ liệu sẽ bị tràn xuống đĩa (Hash Spilling) làm giảm tốc độ.

---

## 🔗 Liên kết Mở rộng
- Khái niệm liên quan: [[Execution Plan]], [[SQL Optimizer]], [[Cost]], [[Statistics (Thống kê Database)]]
- Case study: [[Case - Hai bảng giống nhau nhưng hiệu năng khác nhau]]
