---
title: Cơ chế Khóa trong Database (Locking Mechanisms & Lock Escalation)
aliases:
  - Lock
  - Cơ chế khóa
  - Row Lock
  - Table Lock
  - Lock Escalation
  - Shared Lock
  - Exclusive Lock
  - Intent Lock
tags:
  - database
  - lock
  - concurrency
  - performance
  - core-concept
type: concept
created: 2026-08-26
updated: 2026-08-26
---

# 🔒 Cơ chế Khóa trong Database (Locking Mechanisms)

⬅️ **[[MOC - Concurrency & Lock]]** | 🔗 **[[MOC - Database Overview]]**

---

## 1. Định nghĩa & Mục đích

**Lock (Khóa)** là cơ chế đồng bộ hóa bắt buộc của RDBMS nhằm bảo vệ tính toàn vẹn và nhất quán của dữ liệu (nguyên lý ACID) khi có nhiều giao dịch (Transactions) cùng truy cập và sửa đổi dữ liệu đồng thời.

Nếu không có Lock, hệ thống sẽ gặp các lỗi nghiêm trọng:
- **Lost Update (Mất cập nhật):** Hai giao dịch cùng ghi đè một dòng dữ liệu.
- **Dirty Read (Đọc dữ liệu rác):** Đọc dữ liệu chưa được commit của transaction khác.
- **Non-repeatable Read & Phantom Read:** Dữ liệu bị thay đổi hoặc xuất hiện dòng mới giữa 2 lần đọc trong cùng một transaction.

---

## 2. Phân loại Khóa theo Cấp độ và Mục đích

### 2.1. Phân loại theo Quyền truy cập
1. **Shared Lock (S-Lock / Khóa Đọc):** Được cấp khi một giao dịch đọc dữ liệu. Nhiều giao dịch có thể cùng giữ S-Lock trên một tài nguyên.
2. **Exclusive Lock (X-Lock / Khóa Ghi):** Được cấp khi một giao dịch sửa/xóa dữ liệu (`INSERT`, `UPDATE`, `DELETE`). Chỉ duy nhất 1 giao dịch được giữ X-Lock, tất cả các giao dịch khác (kể cả đọc lẫn ghi) đều phải dừng lại chờ.

### 2.2. Phân loại theo Phạm vi Đối tượng
- **Row-level Lock (Khóa cấp dòng):** Chỉ khóa đúng bản ghi đang thao tác. Tối ưu hiệu năng đồng thời cao nhất.
- **Page/Block-level Lock (Khóa cấp trang):** Khóa toàn bộ Block chứa dữ liệu.
- **Table-level Lock (Khóa cấp bảng):** Khóa toàn bộ bảng dữ liệu. Làm tê liệt toàn bộ các thao tác khác vào bảng.

---

## 3. Hiện tượng Lock Escalation (Khóa Leo Thang)

> [!WARNING]
> **Lock Escalation** là hiện tượng Database Engine tự động chuyển đổi hàng chục nghìn Row Lock thành **1 Table Lock duy nhất**.

**Nguyên nhân:** Mỗi Row Lock tiêu tốn một lượng nhỏ bộ nhớ RAM của hệ thống (Lock Memory Structure). Khi một câu lệnh `UPDATE` hoặc `DELETE` sửa đổi quá nhiều dòng (ví dụ > 5.000 dòng), Database quyết định nâng cấp lên Table Lock để giải phóng bộ nhớ RAM.
👉 **Hậu quả:** Toàn bộ bảng bị khóa cứng, các user khác cố gắng truy cập bảng đều bị treo hệ thống (Wait).

---

## 🔗 Liên kết Mở rộng
- Khái niệm liên quan: [[Deadlock]], [[Foreign Key]], [[Transaction & MVCC]], [[Buffer Cache]]
- Thực chiến: [[Tổng hợp Lock và Deadlock trong Database]], [[Case - Tối ưu Foreign Key và Lock leo thang]], [[Nguyên lý Không va chạm trong tối ưu SQL]]
