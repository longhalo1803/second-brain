---
title: Toàn tập về Index trong Database (Cấu trúc & Phân loại Chỉ mục)
aliases:
  - Index
  - Chỉ mục
  - B-Tree Index
  - Clustered Index
  - Secondary Index
  - Composite Index
  - Covering Index
tags:
  - database
  - index
  - performance
  - sql-tuning
  - core-concept
type: concept
created: 2026-06-18
updated: 2026-08-26
---

# 🔍 Toàn tập về Index (Đánh chỉ mục) trong Cơ sở Dữ liệu

⬅️ **[[MOC - Query Optimization]]** | 🔗 **[[MOC - Storage & Engine]]**

---

## 1. Bản chất Cốt lõi của Index

Khái niệm **Index (Chỉ mục)** có mối liên hệ mật thiết với khái niệm **[[Block (Page)]]**. Nếu [[Block (Page)]] là các "trang giấy A4" chứa dữ liệu nằm lộn xộn trong một quyển sổ lớn, thì Index chính là **Mục lục tra cứu** giúp Database không phải lật mở từng trang giấy A4 một cách mù quáng.

Bản chất của Index là Database **tạo ra một cấu trúc dữ liệu phụ trợ nhỏ gọn hơn**, trích xuất riêng các cột cần tìm kiếm kèm theo một mã định danh tọa độ vật lý (**Row ID / Pointer**) trỏ chính xác về vị trí Block chứa bản ghi gốc.

> [!IMPORTANT]
> **Đặc điểm tối quan trọng của Index:** Dữ liệu trong Index **luôn được tự động sắp xếp theo thứ tự (Sorted)**.

---

## 2. Cấu trúc Vật lý Bên trong của B-Tree Index

Hầu hết các Index trong RDBMS được tổ chức theo cấu trúc kết hợp giữa **Cây cân bằng (Balanced Tree - B-Tree)** và **Danh sách liên kết đôi (Doubly Linked List)**:

```
                      [ Root Node (Gốc) ]
                           /        \
              [ Branch Node ]      [ Branch Node ] (Nhánh)
                 /        \          /        \
           [ Leaf 1 ] <---> [ Leaf 2 ] <---> [ Leaf 3 ] (Lá & Doubly Linked List)
```

1. **Cây B-Tree (Hạ cánh thẳng đứng - Vertical Traverse):** Từ Root Node -> Branch Node -> Leaf Node. Quãng đường từ gốc đến mọi nút lá là như nhau (độ sâu thông thường chỉ 3 - 4 tầng kể cả với bảng hàng chục triệu dòng). Giúp tìm ra bản ghi đầu tiên trong tích tắc (Cực nhanh).
2. **Danh sách liên kết đôi (Quét ngang - Horizontal Scan):** Tại tầng Nút lá (Leaf Nodes), các block Index móc nối với nhau theo cả 2 chiều (trước - sau). Nhờ dữ liệu đã sắp xếp, Database chỉ cần trượt ngang qua trái/phải để gom toàn bộ các bản ghi thỏa điều kiện mà không cần duyệt lại cây.

---

## 3. Phân loại các Loại Index Phổ biến

### 3.1. Primary Index (Chỉ mục Khóa chính)
![[Pasted image 20260619132308.png]]
Tự động tạo ra khi định nghĩa `PRIMARY KEY`. Đảm bảo tính duy nhất (Unique) và sắp xếp tăng dần.

### 3.2. Secondary Index (Non-clustered Index)
![[Pasted image 20260619132330.png]]
Tạo trên các cột tìm kiếm thông thường (`City`, `Created_At`). Tồn tại độc lập với bảng gốc và lưu con trỏ RowID trỏ về vị trí dữ liệu thực.

### 3.3. Clustered Index (Chỉ mục Cụm)
![[Pasted image 20260619132722.png|556]]
Trong MySQL InnoDB hoặc SQL Server, Clustered Index quyết định **trật tự sắp xếp vật lý** của toàn bộ bảng. Dữ liệu các cột thực tế nằm ngay tại các Nút lá của Clustered Index. Mỗi bảng chỉ có **duy nhất 1 Clustered Index**.

### 3.4. Composite Index (Index Tổ hợp)
![[Pasted image 20260619132827.png]]
Index được tạo trên nhiều cột cùng lúc, ví dụ `INDEX (Department_ID, Salary)`.
- **Nguyên tắc Cột dẫn đầu (Leading Column):** Index chỉ có tác dụng khi câu lệnh lọc theo cột đứng đầu (`Department_ID`). Nếu lọc riêng theo `Salary`, Index sẽ bị vô hiệu hóa hoàn toàn!

### 3.5. Covering Index (Index Bao phủ)
![[Pasted image 20260619133221.png]]
Là kỹ thuật đưa toàn bộ các cột xuất hiện trong câu `SELECT` vào trong Index.
👉 **Lợi ích tối thượng:** Database lấy đủ 100% dữ liệu ngay tại tầng Nút lá của Index và **loại bỏ hoàn toàn bước Table Access by RowID (Random I/O)**.

---

## 4. Cú pháp Quản lý Index trong SQL (Syntax)

```sql
-- 1. Tạo Single Column Index
CREATE INDEX idx_product_id ON Sales (product_id);

-- 2. Tạo Composite Index
CREATE INDEX idx_dept_salary ON Employees (department_id, salary);

-- 3. Tạo Unique Index
CREATE UNIQUE INDEX idx_user_email ON Users (email);

-- 4. Xem danh sách Index của bảng
SHOW INDEXES FROM Sales; -- MySQL
-- hoặc dùng sp_helpindex 'Sales' trên SQL Server

-- 5. Xóa Index
DROP INDEX idx_product_id ON Sales;

-- 6. Tái xây dựng Index (Rebuild Index chống phân mảnh)
ALTER INDEX idx_product_id ON Sales REBUILD;
```

---

## 5. Khi nào Index Phản tác dụng? (Ô tô tải vs Xe máy)

![[Pasted image 20260618025349.png|0]]

- Nếu điều kiện tìm kiếm trả về **quá nhiều dữ liệu** (> 15% - 20% tổng số dòng của bảng), việc dùng Index giống như đi "xe máy" chở từng dòng dữ liệu và nhảy Random I/O liên tục vào ổ cứng.
- Lúc này, Optimizer sẽ thông minh từ chối Index để sử dụng **[[Full Table Scan]]** (như chiếc ô tô tải) quét một mạch toàn bộ Block với tốc độ Multi-block Sequential Read cực nhanh.
👉 Xem chi tiết tại: **[[Case - Khi nào Index phản tác dụng (Ô tô tải vs Xe máy)]]**.

---

## 🔗 Liên kết Liên quan
- Khái niệm liên quan: [[Block (Page)]], [[Data Access Methods]], [[Execution Plan]], [[Cost]]
- Nguyên lý & Thực chiến: [[Tư duy tối ưu Database (Database Tuning Mindset)]], [[Case - Khi nào Index phản tác dụng (Ô tô tải vs Xe máy)]]
