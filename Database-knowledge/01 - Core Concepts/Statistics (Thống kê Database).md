---
title: Statistics trong Database (Thông số Thống kê Dữ liệu)
aliases:
  - Statistics
  - Thống kê Database
  - Optimizer Statistics
  - DB Statistics
  - Stale Statistics
tags:
  - database
  - optimizer
  - performance
  - core-concept
type: concept
created: 2026-08-26
updated: 2026-08-26
---

# 📊 Khái niệm Statistics trong Cơ sở Dữ liệu

⬅️ **[[MOC - Query Optimization]]** | 🔗 **[[MOC - Database Overview]]**

---

## 1. Định nghĩa

**Statistics (Bản thống kê dữ liệu)** là tập hợp các siêu dữ liệu (Metadata) mô tả trạng thái vật lý và phân bố giá trị thực tế của các Table, Column và Index trong Database.

**[[SQL Optimizer]]** hoàn toàn "mù" đối với dữ liệu thực tế nếu không có Statistics. Nó không bao giờ tự động quét qua 10 triệu dòng để đếm trước khi chạy lệnh; nó chỉ nhìn vào bản ghi Statistics để đưa ra quyết định lập **[[Execution Plan]]**.

---

## 2. Các Chỉ số Thống kê Quan trọng Nhất

1. **Số lượng bản ghi (Row Count / Cardinality):** Tổng số dòng hiện có trong bảng.
2. **Số lượng [[Block (Page)]] (Block Count):** Tổng số trang vật lý mà bảng đang chiếm dụng trên đĩa.
3. **Number of Distinct Values (NDV):** Số lượng giá trị khác nhau trong một cột (quyết định độ chọn lọc - Selectivity).
4. **Histograms (Biểu đồ phân bố tần suất):** Mô tả sự phân bố dữ liệu không đồng đều (Data Skew) để xử lý các cột có giá trị lệch nhiều.
5. **Độ sâu cây Index (B-Tree Level / Clustering Factor):** Độ cao của cây Index và mức độ đồng bộ trật tự vật lý giữa Index và Table.

---

## 3. Thảm họa "Stale Statistics" (Thống kê Lạc hậu)

Khi bạn thực hiện đổ dữ liệu lớn (Batch Insert / Data Migration), số lượng dòng thực tế tăng từ 0 lên 17 triệu dòng nhưng thông số thống kê chưa được cập nhật:
- Optimizer vẫn tưởng bảng chỉ có 0 dòng.
- Nó quyết định dùng thuật toán `[[Nested Loop Join]]`.
- **Hậu quả:** Hệ thống bị treo cứng, cạn kiệt tài nguyên CPU và RAM.

👉 Xem chi tiết Case Study kinh điển: **[[Case - Hai bảng giống nhau nhưng hiệu năng khác nhau]]**.

---

## 🔗 Liên kết Mở rộng
- Khái niệm liên quan: [[SQL Optimizer]], [[Cost]], [[Execution Plan]], [[Join Methods]]
- Case study: [[Case - Hai bảng giống nhau nhưng hiệu năng khác nhau]]
