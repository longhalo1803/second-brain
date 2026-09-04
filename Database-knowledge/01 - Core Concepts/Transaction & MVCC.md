---
title: Giao dịch & Cơ chế MVCC trong Database (Multi-Version Concurrency Control)
aliases:
  - Transaction & MVCC
  - MVCC
  - Multi-Version Concurrency Control
  - Transaction
  - Giao dịch Database
  - Dead Tuples
  - Read View
tags:
  - database
  - concurrency
  - mvcc
  - transaction
  - core-concept
type: concept
created: 2026-06-25
updated: 2026-08-26
---

# 🔄 Giao dịch & Cơ chế MVCC (Multi-Version Concurrency Control)

⬅️ **[[MOC - Concurrency & Lock]]** | 🔗 **[[MOC - Storage & Engine]]**

---

## 1. Bài toán Kinh điển: Làm sao Đọc không Chặn Ghi?

Trong các hệ thống RDBMS truyền thống, khi một giao dịch đang `UPDATE` dữ liệu, nó phải khóa dòng dữ liệu đó lại bằng Exclusive Lock (X-Lock), khiến các giao dịch `SELECT` khác phải dừng lại chờ đợi (Bị Lock nghẽn).

Để giải quyết triệt để vấn đề này, các Database hiện đại (PostgreSQL, MySQL InnoDB, Oracle, SQL Server Snapshot) áp dụng cơ chế **MVCC (Kiểm soát đồng thời đa phiên bản)**.

> [!TIP]
> **Triết lý MVCC:** _"Readers do not block Writers, and Writers do not block Readers."_ (Người Đọc không bao giờ chặn người Ghi, và người Ghi không bao giờ chặn người Đọc).

---

## 2. Cơ chế Hoạt động của MVCC

Mỗi khi có thao tác thêm/sửa/xóa, Database không ghi đè trực tiếp lên dữ liệu cũ mà sinh ra một **phiên bản mới (Version)**:

- **Khi INSERT:** Tạo một dòng mới với dấu mốc Transaction ID tạo (`xmin` / `created_tx`).
- **Khi UPDATE:** Tạo một bản ghi mới với giá trị mới, và đánh dấu bản ghi cũ là **"Dead Tuple" (Bản ghi chết/rác)** bằng cách gán `xmax` / `deleted_tx`.
- **Khi DELETE:** Không xóa vật lý dữ liệu ngay, mà chỉ đánh dấu bản ghi đó là đã chết (`xmax = current_tx`).
- **Khi SELECT (Read View / Snapshot):** Database tạo một bản chụp (Snapshot) tại thời điểm bắt đầu truy vấn. Người dùng chỉ nhìn thấy các bản ghi đã commit trước thời điểm đó, hoàn toàn phớt lờ các bản ghi đang bị sửa đổi của các transaction khác.

---

## 3. Cái giá phải trả của MVCC: Rác và Phình Bảng (Table Bloat)

Vì các bản ghi cũ không bị xóa vật lý ngay, sau hàng triệu thao tác Update/Delete, ổ đĩa sẽ chứa đầy **Dead Tuples**:

- Bảng thực tế chỉ có vài nghìn dòng sử dụng, nhưng dung lượng chiếm hàng chục Gigabyte.
- Để dọn dẹp các Dead Tuples này, Database cần đến **Tiến trình Dọn rác**.
  👉 Xem chi tiết tại: **[[VACUUM & Dọn rác Database]]**.

---

## 🔗 Liên kết Mở rộng

- Khái niệm liên quan: [[Write-Ahead Logging (WAL)]], [[VACUUM & Dọn rác Database]], [[Lock]], [[Deadlock]], [[Block (Page)]]
- Nguyên lý & Thực chiến: [[Vận hành ngầm của câu lệnh DML (INSERT Internals)]], [[Case - Table 0 row nhưng truy vấn vẫn cực chậm]]
