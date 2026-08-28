---
title: Record và Tuple trong Database (Đơn vị Bản ghi Dữ liệu)
aliases:
  - Record
  - Tuple
  - Row
  - Dòng dữ liệu
  - Bản ghi
tags:
  - database
  - storage
  - architecture
  - core-concept
type: concept
created: 2026-06-18
updated: 2026-08-26
---

# 📝 Khái niệm Record / Row / Tuple trong Database

⬅️ **[[MOC - Storage & Engine]]** | 🔗 **[[MOC - Database Overview]]**

---

## 1. Định nghĩa

Khái niệm **Record (Bản ghi)** hay **Row (Dòng dữ liệu)** / **Tuple** là đơn vị đại diện cho thông tin của một đối tượng cụ thể được lưu trữ trong bảng (Table) của cơ sở dữ liệu.

- Trong RDBMS (Oracle, PostgreSQL, MySQL, SQL Server): Được gọi là **Row** hoặc **Tuple**.
- Trong NoSQL (MongoDB, DynamoDB): Được gọi là **Document** hoặc **Item**.

![[Pasted image 20260618025705.png]]

![[Pasted image 20260618025803.png]]

---

## 2. Mối quan hệ Vật lý giữa Record và [[Block (Page)]]

- **Record** là nội dung logic mà lập trình viên nhìn thấy và thao tác qua SQL.
- **[[Block (Page)]]** là container vật lý chứa nhiều Record.

```
+--------------------------------------------------------------+
|                    BLOCK / PAGE (Ví dụ: 8KB)                 |
|  +--------------------------------------------------------+  |
|  | Record 1: [ID: 1, Name: "An", Age: 25, Role: "Dev"]    |  |
|  +--------------------------------------------------------+  |
|  | Record 2: [ID: 2, Name: "Bình", Age: 30, Role: "Lead"] |  |
|  +--------------------------------------------------------+  |
|  | Record 3: [ID: 3, Name: "Cường", Age: 28, Role: "QA"]  |  |
|  +--------------------------------------------------------+  |
+--------------------------------------------------------------+
```

Khi bạn cần tìm Record của một nhân viên tên "An", Database không thể "cắt" riêng bản ghi số 1 mang về. Database bắt buộc phải **nạp toàn bộ Block chứa bản ghi đó (cùng với bản ghi của Bình và Cường)** lên [[Buffer Cache]] trên RAM.

---

## 3. Các Vấn đề Hiệu năng Cần Lưu ý về Record

### 3.1. Row Chaining (Nối dòng)
Xảy ra khi kích thước của một Record **vượt quá kích thước của 1 Block** (ví dụ: Record chứa các cột text dài, JSON, BLOB có kích thước 20KB trong khi Block chỉ có 8KB). Database buộc phải chia Record này thành nhiều mảnh và lưu trữ rải rác trên nhiều Block khác nhau, nối với nhau bằng con trỏ.
👉 **Hậu quả:** Để đọc 1 dòng duy nhất, Database phải thực hiện nhiều lần I/O đĩa.

### 3.2. Row Migration (Di cư dòng)
Xảy ra khi một Record ban đầu có kích thước nhỏ, nhưng sau đó lệnh `UPDATE` làm dung lượng dòng tăng lên trong khi Block hiện tại không còn đủ Free Space (PCTFREE). Database phải chuyển toàn bộ dữ liệu dòng sang một Block mới hoàn toàn, và để lại một con trỏ (Pointer) ở Block cũ.
👉 **Hậu quả:** Khi truy vấn theo Index trỏ vào RowID cũ, Database phải tốn thêm 1 bước nhảy (Double Hop) sang Block mới để lấy dữ liệu.

### 3.3. Lầm tưởng: "Bảng ít Record thì chắc chắn câu lệnh chạy nhanh"
Tốc độ truy vấn không phụ thuộc vào số lượng Record trả về, mà phụ thuộc vào **số lượng Block** mà câu lệnh phải duyệt qua. Một bảng có 0 record nhưng chiếm 200.000 Block vẫn chạy cực kỳ chậm (Xem: **[[Case - Table 0 row nhưng truy vấn vẫn cực chậm]]**).

---

## 🔗 Liên kết Liên quan
- Khái niệm liên quan: [[Block (Page)]], [[Buffer Cache]], [[Index]], [[VACUUM & Dọn rác Database]]
- Trường hợp thực tế: [[Case - Table 0 row nhưng truy vấn vẫn cực chậm]]
