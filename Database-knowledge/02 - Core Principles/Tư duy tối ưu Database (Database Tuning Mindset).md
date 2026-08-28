---
title: Tư duy Tối ưu Database (Database Tuning Mindset cho Developer)
aliases:
  - Tư duy tối ưu Database
  - Database Tuning Mindset
  - Database Tunning Mindset
  - Cách Database nghĩ
  - Tuning Mindset
tags:
  - database
  - performance_tuning
  - mindset
  - wecommit
  - career_advice
type: principle
author: Trần Quốc Huy - Wecommit
created: 2026-06-25
updated: 2026-08-26
link: https://youtu.be/aRkidzUZ-gg?si=c2hXj0i-id9qn6qt
---

# 🧠 Tư duy Tối ưu Database (Database Tuning Mindset)

⬅️ **[[MOC - Database Overview]]** | 🔗 **[[MOC - Query Optimization]]**

---

## 1. Chuyển đổi Góc nhìn: Từ Lập trình viên sang Database Engine

Đa số lập trình viên tiếp cận tối ưu Database bằng cảm tính: "Thấy câu lệnh chậm thì thêm Index", "Bảng ít dòng thì chắc chắn nhanh", "Code chạy ở Dev nhanh thì lên Production cũng nhanh".

Để trở thành chuyên gia tối ưu hoặc Solution Architect, bạn phải học cách **nhìn thế giới qua lăng kính của Database**:

```
  Góc nhìn của Lập trình viên (Dev)       Góc nhìn của Database Engine
  ---------------------------------       ----------------------------
  - Quan tâm số dòng dữ liệu (Rows)  ---> - Quan tâm số trang dữ liệu (Blocks)
  - Viết code SQL đúng cú pháp logic ---> - Phân tích chi phí (Cost) & Execution Plan
  - Cứ tạo Index là câu lệnh sẽ dùng ---> - Cân nhắc Random I/O vs Sequential Read
  - Thấy chậm thì đổ lỗi cho phần cứng---> - Kiểm tra hàng chờ tranh chấp (Wait Events)
```

---

## 2. Sự thật 1: Không phải cứ ít [[Record (Tuple)]] (Row) là sẽ Nhanh

Database chỉ đọc và ghi theo đơn vị **[[Block (Page)]]**. Một bảng dù chỉ có 0 bản ghi hoặc 5 bản ghi, nhưng nếu nằm rải rác trên 200.000 Block chưa được dọn dẹp, Database vẫn phải tốn hàng giây để quét qua toàn bộ các Block đó.

👉 Đọc chi tiết bài học thực chứng: **[[Case - Table 0 row nhưng truy vấn vẫn cực chậm]]**.

---

## 3. Sự thật 2: Tại sao có Index nhưng Database Quyết định Ngó lơ?

Rất nhiều Dev bức xúc: *"Tôi đã tạo Index trên cột đó rồi, tại sao câu lệnh vẫn chạy Full Table Scan?"*

**Lý do:** Trình tối ưu (**[[SQL Optimizer]]**) tính toán thấy rằng:
- Dữ liệu bạn cần lấy chiếm tỷ lệ lớn trong bảng (ví dụ > 20%).
- Việc dùng Index sẽ bắt Database phải làm thao tác **xe máy chở từng chuyến (Random I/O)** nhảy từ Index về Table hàng triệu lần.
- Database quyết định từ chối Index để dùng **xe tải lớn ([[Full Table Scan]])** quét một lèo toàn bộ bảng nhanh hơn gấp nhiều lần!

👉 Đọc chi tiết bài học thực chứng: **[[Case - Khi nào Index phản tác dụng (Ô tô tải vs Xe máy)]]**.

---

## 4. Sự thật 3: Cùng Bảng, Cùng Dữ liệu, Cùng SQL nhưng đổi Database thì Tốc độ khác hẳn

Tại sao chạy trên PostgreSQL thì nhanh mà sang MySQL lại chậm, hoặc chạy trên Oracle thì mượt mà sang SQL Server lại bị Lock?
- Khác biệt về cơ chế khóa mặc định và kiến trúc bộ nhớ ([[Database Instance]]).
- Khác biệt về giải thuật dọn rác ([[VACUUM & Dọn rác Database]] vs Purge).
- Khác biệt về thuật toán Join ([[Join Methods]]) và bộ tính toán chi phí ([[Cost]]).

---

## 🔗 Liên kết Điều hướng
- MOC liên quan: [[MOC - Database Overview]], [[MOC - Query Optimization]]
- Bài học liên quan: [[Nguyên lý 3+2 trong Database]], [[3 Yếu tố cốt lõi làm Database nhanh]], [[Quy trình 6 bước xử lý câu lệnh SQL]]
