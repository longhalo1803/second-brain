---
title: Case Study - Khi nào Index Phản tác dụng (Bài toán Ô tô tải vs Xe máy)
aliases:
  - Khi nào Index phản tác dụng
  - Bài toán Ô tô tải vs Xe máy
  - Low Selectivity Index
  - Index vs Full Table Scan
tags:
  - database
  - index
  - performance
  - sql-tuning
  - case-study
type: case-study
created: 2026-08-26
updated: 2026-08-26
---

# 💥 Case Study: Khi nào Index Phản tác dụng? (Ô tô tải vs Xe máy)

⬅️ **[[MOC - Query Optimization]]** | 🔗 **[[MOC - Storage & Engine]]**

---

## 1. Ảo tưởng Phổ biến: "Cứ có Index là Truy vấn sẽ Nhanh"

Nhiều lập trình viên cho rằng thêm Index vào bất kỳ cột nào có trong mệnh đề `WHERE` cũng sẽ làm câu lệnh chạy nhanh hơn. Đây là một sai lầm nghiêm trọng về mặt vật lý.

---

## 2. Hình ảnh Ẩn dụ: Chiếc Xe Máy và Xe Tải

```
[ Dùng B-Tree Index ] = CHIẾC XE MÁY
- Đến mục lục lấy 1 địa chỉ -> Chạy xe máy vào ngõ lấy 1 món hàng.
- Lặp lại quy trình: Đi đi về về liên tục 1 triệu lần (Random I/O).
-> Cực nhanh nếu chỉ lấy 1 - 5 món hàng.
-> CỰC CHẬM VÀ KIỆT SỨC nếu phải chở 1 triệu món hàng!

[ Dùng Full Table Scan ] = CHIẾC Ô TÔ TẢI
- Không cần xem mục lục.
- Cho xe tải lớn chạy một mạch từ đầu đường đến cuối đường, gom sạch toàn bộ hàng lên xe trong một lần chạy duy nhất (Sequential Multi-block Read).
-> Nhanh hơn xe máy gấp hàng chục lần khi cần lấy khối lượng hàng lớn!
```

---

## 3. Độ Chọn lọc (Selectivity) - Ngưỡng Ranh giới của Optimizer

Độ chọn lọc (**Selectivity**) là tỷ lệ phần trăm số bản ghi thỏa mãn điều kiện lọc so với tổng số bản ghi của bảng:

$$	ext{Selectivity} = rac{	ext{Số dòng thỏa điều kiện}}{	ext{Tổng số dòng của bảng}} 	imes 100\%$$

- **High Selectivity (Độ chọn lọc cao, ví dụ < 5%):** Kết quả trả về rất ít dòng (ví dụ tìm theo `email`, `CMND/CCCD`, `order_id`). Dùng **[[Index]]** là tối ưu nhất.
- **Low Selectivity (Độ chọn lọc thấp, ví dụ > 15% - 20%):** Kết quả trả về chiếm tỷ lệ lớn trong bảng (ví dụ: `gender = 'MALE'`, `status = 'ACTIVE'` chiếm 80% bảng). Việc dùng Index sẽ sinh ra lượng **Random I/O** khổng lồ, khiến hệ thống chạy chậm hơn nhiều so với **[[Full Table Scan]]**.

---

## 4. Bài học Rút ra

1. **Không đánh Index trên các cột có độ phân tán thấp (Low Cardinality):** Như cột Giới tính, Trạng thái (Active/Inactive), Cờ Yes/No.
2. **Tôn trọng quyết định của Optimizer:** Khi thấy Optimizer chọn Full Table Scan thay vì dùng Index bạn đã tạo, hãy kiểm tra lại Selectivity của dữ liệu thay vì cố tình dùng Hint (`/*+ INDEX */`) để ép Database chạy theo ý mình.

---

## 🔗 Liên kết Liên quan
- Khái niệm nền tảng: [[Index]], [[Block (Page)]], [[Data Access Methods]], [[Cost]], [[SQL Optimizer]]
- Nguyên lý & Thực chứng: [[Tư duy tối ưu Database (Database Tuning Mindset)]], [[Nguyên lý 3+2 trong Database]], [[Tại sao Database không chọn Index (Bản chất Cost-Based Optimizer)]]
