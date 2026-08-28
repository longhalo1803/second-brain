---
title: Tiến trình VACUUM & Dọn rác trong Database (Garbage Collection)
aliases:
  - VACUUM & Dọn rác Database
  - VACUUM
  - Dọn rác Database
  - Tiến trình dọn rác (VACUUM)
  - Tiến trình dọn rác (VACUMM)
  - Giải mã VACUUM trong PostgreSQL
  - Table Bloat
tags:
  - database
  - postgresql
  - performance
  - vacuum
  - mvcc
  - core-concept
type: concept
created: 2026-06-25
updated: 2026-08-26
---

# 🧹 Tiến trình VACUUM & Dọn rác trong Cơ sở Dữ liệu

⬅️ **[[MOC - Storage & Engine]]** | 🔗 **[[MOC - Concurrency & Lock]]**

---

## 1. Nguồn gốc của "Rác" trong Database

Như đã phân tích tại **[[Transaction & MVCC]]**, để phục vụ việc nhiều giao dịch đọc/ghi đồng thời mà không bị khóa chờ nhau, các database như PostgreSQL không bao giờ ghi đè trực tiếp khi `UPDATE` hoặc xóa vật lý tức thì khi `DELETE`. Thay vào đó, hệ thống tạo phiên bản mới và đánh dấu bản ghi cũ là **Dead Tuple (Bản ghi rác)**.

Trong các hệ thống OLTP có hàng triệu giao dịch mỗi ngày, nếu không có cơ chế dọn rác định kỳ, hệ thống sẽ rơi vào thảm cảnh: **Dữ liệu thực tế sử dụng thì ít, nhưng ổ cứng phình to (Table Bloat) và truy vấn quét bảng thì chậm như rùa.**

---

## 2. Cơ chế Hoạt động của VACUUM (Trong PostgreSQL)

PostgreSQL cung cấp 2 cơ chế dọn rác chính:

### 2.1. Standard VACUUM (Autovacuum chạy ngầm)
- Quét qua các [[Block (Page)]] để tìm các Dead Tuples không còn phiên làm việc nào cần đọc tới.
- Đánh dấu các khoảng trống đó thành **Free Space** để các lệnh `INSERT` / `UPDATE` tương lai có thể tái sử dụng ghi đè lên.
- Cập nhật bản đồ **Free Space Map (FSM)** và **Visibility Map (VM)**.
- **Đặc điểm:** Chạy song song không khóa bảng (Non-blocking), không làm gián đoạn hệ thống. Nhưng **không trả lại dung lượng ổ cứng cho Hệ điều hành (OS)**.

### 2.2. VACUUM FULL
- Tạo một bản sao mới hoàn toàn của bảng trên đĩa, chỉ copy các bản ghi đang sống (Live Tuples) sang, sau đó xóa file cũ.
- **Đặc điểm:** Giải phóng 100% dung lượng đĩa trống trả về cho OS.
- **Nguy hiểm:** Khóa độc quyền toàn bộ bảng (**Access Exclusive Lock**), cấm mọi thao tác đọc ghi cho đến khi chạy xong.

---

## 3. Thảm họa "Table 0 row vẫn chậm" do Thiếu VACUUM

Khi bạn xóa sạch 10 triệu dòng bằng lệnh `DELETE FROM orders;`:
- Bảng trả về `0 row`.
- Nhưng hàng trăm nghìn [[Block (Page)]] chứa Dead Tuples vẫn nằm nguyên trên ổ cứng.
- Khi chạy `SELECT * FROM orders;`, `[[SQL Optimizer]]` buộc phải dùng `[[Full Table Scan]]` đọc toàn bộ hàng trăm nghìn Block rỗng này nạp lên RAM, khiến câu lệnh chạy mất vài giây đến vài phút dù bảng không có dữ liệu!

👉 Xem chi tiết cách xử lý tại: **[[Case - Table 0 row nhưng truy vấn vẫn cực chậm]]**.

---

## 🔗 Liên kết Mở rộng
- Khái niệm liên quan: [[Transaction & MVCC]], [[Block (Page)]], [[Full Table Scan]], [[Lock]]
- Case study: [[Case - Table 0 row nhưng truy vấn vẫn cực chậm]]
