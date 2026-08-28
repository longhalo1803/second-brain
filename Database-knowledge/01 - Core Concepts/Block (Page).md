---
title: Block và Page trong Database (Đơn vị I/O Vật lý)
aliases:
  - Block
  - Page
  - Data Block
  - Page/Block
  - Data Page
tags:
  - database
  - storage
  - architecture
  - core-concept
type: concept
created: 2026-06-18
updated: 2026-08-26
---

# 🧱 Khái niệm Block / Page trong Cơ sở Dữ liệu

⬅️ **[[MOC - Storage & Engine]]** | 🔗 **[[MOC - Database Overview]]**

---

## 1. Định nghĩa Cốt lõi

Khái niệm **Block (hoặc Page)** là **đơn vị vật lý nhỏ nhất** mà một hệ quản trị cơ sở dữ liệu (RDBMS) sử dụng để quản lý, lưu trữ, và thực hiện việc đọc/ghi (I/O) dữ liệu giữa Ổ đĩa (Disk) và Bộ nhớ RAM ([[Buffer Cache]]).

- Trong **Oracle Database**, đơn vị này được gọi là **Data Block** (phổ biến là 8KB).
- Trong **PostgreSQL**, đơn vị này được gọi là **Page** (mặc định là 8KB).
- Trong **MySQL (InnoDB Engine)**, đơn vị này được gọi là **Page** (mặc định là 16KB).
- Trong **SQL Server**, đơn vị này được gọi là **Page** (8KB) và gộp 8 Page thành 1 **Extent** (64KB).

![[Pasted image 20260618025054.png]]

---

## 2. Quy luật Bất biến: Database không làm việc theo từng Dòng (Row)

Khi lập trình viên viết câu lệnh `SELECT name FROM users WHERE id = 10;`, nhiều người lầm tưởng database sẽ chỉ chui xuống đĩa đọc đúng 1 dòng (Row) của user đó.

> [!IMPORTANT]
> **Sự thật vật lý:** Database **KHÔNG BAO GIỜ** đọc hoặc ghi một bản ghi đơn lẻ trực tiếp từ ổ cứng. Mọi thao tác nạp dữ liệu luôn diễn ra theo **đơn vị nguyên vẹn 1 Block**.

![[Pasted image 20260618024834.png]]

### 📖 Hình ảnh Ẩn dụ: Quyển sách và Trang giấy
- Hãy tưởng tượng toàn bộ Database của bạn là một **Quyển sách dày cộp**.
- Mỗi **[[Block (Page)]]** chính là một **Trang giấy A4** trong quyển sách đó.
- Mỗi **[[Record (Tuple)]]** là một **Dòng chữ** được viết trên trang A4.

Khi bạn muốn đọc dòng chữ thứ 5 trên trang 100, bạn không thể xé đúng dòng chữ đó ra đọc; bạn bắt buộc phải **lật mở toàn bộ trang giấy A4 số 100** đặt lên bàn làm việc (bộ nhớ RAM) rồi mới đọc nội dung bên trong.

---

## 3. Cấu trúc Giải phẫu Bên trong một Block (Block Structure)

Một Block không chỉ chứa dữ liệu thuần túy mà được chia làm 3 phần:

```
+-------------------------------------------------------+
| 1. Block Header (Metadata, Transaction Slots, ITL)    |
+-------------------------------------------------------+
| 2. Free Space (Khoảng trống để dòng dữ liệu giãn nở)  |
+-------------------------------------------------------+
| 3. Row Data (Dữ liệu các dòng được chèn từ dưới lên)  |
+-------------------------------------------------------+
```

1. **Header (Phần đầu):** Chứa thông tin quản lý loại block, địa chỉ vật lý, danh sách các transaction đang thao tác trên block (ITL - Interested Transaction List).
2. **Free Space (Khoảng trống dự phòng - PCTFREE):** Khoảng trống để phục vụ cho các lệnh `UPDATE` làm tăng kích thước của các dòng đã có trong block mà không bị vỡ trang.
3. **Row Data (Phần thân):** Chứa dữ liệu thực tế của các [[Record (Tuple)]].

---

## 4. Tại sao Block là Chìa khóa của Mọi bài toán Hiệu năng?

1. **Tốc độ phụ thuộc số lượng Block phải quét:** Một câu lệnh nhanh hay chậm không phụ thuộc vào việc nó trả về 1 dòng hay 100 dòng, mà phụ thuộc vào việc nó phải nạp bao nhiêu Block từ Ổ đĩa vào RAM.
2. **Hiện tượng Bảng 0 row vẫn chậm (High Water Mark):** Khi bạn dùng lệnh `DELETE` toàn bộ dữ liệu, các dòng chữ bị xóa nhưng hàng triệu trang A4 rỗng (Block) vẫn còn nguyên vẹn trong sách. Khi chạy `SELECT *`, Database vẫn phải duyệt qua toàn bộ số Block này (Xem chi tiết tại: **[[Case - Table 0 row nhưng truy vấn vẫn cực chậm]]**).
3. **Đánh đổi giữa [[Index]] và [[Full Table Scan]]:**
   - Dùng Index: Nhảy dù vào đúng Block chứa dữ liệu (tốn Random I/O).
   - Dùng Full Table Scan: Đọc tuần tự hàng loạt Block liên tiếp (Multi-block Read / Sequential I/O).

---

## 🔗 Liên kết & Khái niệm Mở rộng
- Khái niệm liên quan: [[Record (Tuple)]], [[Buffer Cache]], [[Cost]], [[Index]], [[Data Access Methods]]
- Nguyên lý ứng dụng: [[Nguyên lý 3+2 trong Database]], [[Tư duy tối ưu Database (Database Tuning Mindset)]]
