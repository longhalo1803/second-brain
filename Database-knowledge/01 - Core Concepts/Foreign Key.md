---
title: Hiệu năng Khóa Ngoại trong Database (Foreign Key Performance & Indexing)
aliases:
  - Foreign Key
  - Khóa ngoại
  - Hiệu năng Foreign Key
  - FK Performance
  - Unindexed Foreign Key
tags:
  - database
  - foreign-key
  - lock
  - performance
  - core-concept
type: concept
created: 2026-08-26
updated: 2026-08-26
---

# 🔑 Hiệu năng Khóa Ngoại (Foreign Key) trong RDBMS

⬅️ **[[MOC - Concurrency & Lock]]** | 🔗 **[[MOC - Database Overview]]**

---

## 1. Bản chất Hoạt động của Foreign Key (FK)

**Foreign Key (Khóa ngoại)** là ràng buộc toàn vẹn quan trọng nhất trong mô hình cơ sở dữ liệu quan hệ (RDBMS), đảm bảo rằng một giá trị ở bảng Con (Child Table) bắt buộc phải tồn tại ở bảng Cha (Parent Table).

Tuy nhiên, về mặt vật lý, mỗi khi có thao tác sửa đổi trên bảng Cha hoặc bảng Con, Database Engine phải ngầm thực hiện các bước kiểm tra tính toàn vẹn (Integrity Checks) và **thiết lập các cơ chế Khóa ([[Lock]]) ngầm định**.

### 🔍 Tác động ngầm khi INSERT: Phát sinh Logical Reads trên Bảng Cha

Khi bạn thực hiện câu lệnh chèn dữ liệu vào bảng Con:

```sql
INSERT INTO employees (emp_id, emp_name, department_id) VALUES (10, 'Huy', 5);
```

Dù chỉ ghi vào bảng `employees`, kết quả thống kê I/O (`SET STATISTICS IO ON`) sẽ cho thấy **phát sinh thêm Logical Reads trên bảng cha `departments`**.

- **Bản chất:** Database bắt buộc phải đọc khối dữ liệu hoặc Primary Key Index của bảng Cha để xác minh phòng ban `department_id = 5` có tồn tại hay không.
- Nếu dữ liệu bảng cha chưa có trên [[Buffer Cache]], thao tác `INSERT` đơn giản này sẽ kéo theo **Physical Disk Reads** làm suy giảm tốc độ ghi.
- Xem chi tiết tại: **[[Vận hành ngầm của câu lệnh DML (INSERT Internals)]]**.

---

## 2. Cái Bẫy Tử Huyệt: Thiếu Index trên Cột Khóa Ngoại

> [!CAUTION]
> Hầu hết các RDBMS (như Oracle, PostgreSQL, SQL Server) **KHÔNG TỰ ĐỘNG TẠO INDEX** trên cột Khóa ngoại của Bảng Con khi bạn khai báo ràng buộc `FOREIGN KEY` (chỉ có MySQL InnoDB là tự tạo).

### Kịch bản Thảm họa Treo Hệ thống:

- Giả sử bạn có bảng Cha `CUSTOMERS` (1 triệu dòng) và bảng Con `ORDERS` (20 triệu dòng).
- Bảng `ORDERS` có cột `customer_id` làm khóa ngoại trỏ về `CUSTOMERS`, nhưng **chưa được đánh Index**.
- Khi một giao dịch chạy lệnh `DELETE FROM CUSTOMERS WHERE id = 999;` hoặc `UPDATE` khóa chính:
  1. Database bắt buộc phải kiểm tra xem có đơn hàng nào trong bảng `ORDERS` đang tham chiếu đến `customer_id = 999` hay không.
  2. Vì không có Index, Database phải thực hiện **[[Full Table Scan]]** trên bảng `ORDERS`.
  3. Để đảm bảo không ai chèn đơn hàng mới trong lúc đang quét, Database **KHÓA CỨNG TOÀN BỘ BẢNG ORDERS (Table-level Share Lock)**!
  4. **Hậu quả:** Toàn bộ hệ thống đặt hàng online bị đóng băng, hàng nghìn giao dịch khác bị nghẽn và gây ra lỗi tràn kết nối (Connection Pool Exhaustion).

---

## 3. Giải pháp Khắc phục

1. **Luôn luôn tạo Index trên tất cả các cột Foreign Key** ở bảng Con.
2. Với các hệ thống Big Data / High Throughput (như Microservices, Core Banking), cân nhắc chuyển việc kiểm tra toàn vẹn lên tầng Ứng dụng (Application Layer) và bỏ ràng buộc FK vật lý để giải phóng chi phí Lock.

👉 Xem phân tích chi tiết tại: **[[Case - Tối ưu Foreign Key và Lock leo thang]]**.

---

## 🔗 Liên kết Mở rộng

- Khái niệm liên quan: [[Lock]], [[Deadlock]], [[Index]], [[Full Table Scan]]
- Thực chiến: [[Case - Tối ưu Foreign Key và Lock leo thang]], [[Tổng hợp Lock và Deadlock trong Database]]
