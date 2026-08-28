---
title: Case Study - Table 0 row nhưng câu lệnh SQL vẫn RẤT CHẬM
aliases:
  - Table 0 row - câu lệnh SQL vẫn RẤT CHẬM
  - Table 0 row vẫn chậm
  - Bảng 0 row vẫn chậm
  - Case Table 0 row
tags:
  - database
  - tran-quoc-huy
  - architecture
  - performance
  - case-study
type: case-study
author: Trần Quốc Huy - Wecommit
created: 2026-06-30
updated: 2026-08-26
link: https://youtu.be/xSpXYB8v1NY?si=h2LTzOxRPvkiA0ER
---

# 💥 Case Study: Bảng 0 Row nhưng Truy vấn vẫn RẤT CHẬM

⬅️ **[[MOC - Storage & Engine]]** | 🔗 **[[MOC - Database Overview]]**

---

## 1. Hiện tượng Nghịch lý

Một bảng hoàn toàn không có dữ liệu nào (**0 bản ghi / 0 row**), không có ai đang khóa bảng. Khi chạy một câu lệnh truy vấn đơn giản:
```sql
SELECT * FROM vk;
```
Hệ thống mất tới **2 - 3 giây** (thậm chí vài phút trong môi trường thực tế) mới hoàn thành!

---

## 2. Kịch bản Thực chứng (Demo Breakdown)

- **Thiết lập:** Tạo một bảng `vk` với 6 cột dữ liệu đơn giản.
- **Dữ liệu ban đầu:** Đổ hàng triệu dòng dữ liệu vào bảng, sau đó dùng lệnh `DELETE FROM vk;` để xóa sạch toàn bộ.
- **Thực hiện kiểm tra:**
  - Cập nhật lại thông số thống kê (**[[Statistics (Thống kê Database)]]**) để Database nhận diện chính xác bảng đang có 0 bản ghi.
  - Xóa sạch [[Buffer Cache]] trên RAM để ép Database phải đọc trực tiếp từ Ổ đĩa.
- **Kết quả:** Câu lệnh `SELECT * FROM vk;` vẫn chạy cực kỳ chậm!

---

## 3. Nguyên nhân Cốt lõi: Góc nhìn Vật lý của Database

### Đơn vị Làm việc của Database là [[Block (Page)]]
Database không bao giờ làm việc với đơn vị Row. Khi bạn thực hiện lệnh `DELETE`:
1. Dữ liệu các dòng chữ bị xóa, nhưng **các trang giấy A4 (Block) vật lý vẫn còn nguyên vẹn trong file dữ liệu**.
2. Mốc **High Water Mark (HWM)** - mốc đánh dấu dung lượng đỉnh mà bảng từng chiếm giữ - không hề bị hạ xuống.

### Kế hoạch Thực thi: [[Full Table Scan]]
- Câu lệnh `SELECT *` không có điều kiện `WHERE` nên Optimizer bắt buộc phải chọn chiến lược **Full Table Scan**.
- Thuật ngữ "Full" ở đây nghĩa là **quét toàn bộ các Block nằm dưới mốc High Water Mark**, bất kể Block đó có chứa dữ liệu sống hay chỉ chứa Dead Tuples/khoảng trống rỗng!
- Trong bản demo, bảng `vk` chiếm tới **221.000 Blocks** (tương đương khoảng **1,69 GB** dung lượng). Database bắt buộc phải bốc toàn bộ 1,69 GB dữ liệu rỗng này từ Ổ cứng ném lên RAM, gây nghẽn I/O nghiêm trọng.

---

## 4. Giải pháp Xử lý Triệt để

1. **Dùng TRUNCATE thay vì DELETE:** Lệnh `TRUNCATE TABLE vk;` là lệnh DDL, nó giải phóng toàn bộ Block và kéo mốc High Water Mark về vị trí 0 ngay lập tức.
2. **Dọn dẹp và Thu hẹp Bảng (Shrink / VACUUM FULL / Reorganize):**
   - Trong PostgreSQL: Chạy `VACUUM FULL vk;`.
   - Trong Oracle: Chạy `ALTER TABLE vk SHRINK SPACE COMPACT;`.
   - Trong MySQL: Chạy `OPTIMIZE TABLE vk;`.

---

## 🔗 Liên kết Liên quan
- Khái niệm nền tảng: [[Block (Page)]], [[Record (Tuple)]], [[Buffer Cache]], [[VACUUM & Dọn rác Database]]
- Nguyên lý: [[Nguyên lý 3+2 trong Database]], [[Tư duy tối ưu Database (Database Tuning Mindset)]]
