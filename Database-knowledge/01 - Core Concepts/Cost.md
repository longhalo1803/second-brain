---
title: Cost trong Database (Chi phí Thực thi của Optimizer)
aliases:
  - Cost
  - Chi phí thực thi
  - Optimizer Cost
  - Cost Model
tags:
  - database
  - optimizer
  - performance
  - core-concept
type: concept
created: 2026-06-18
updated: 2026-08-26
---

# ⚖️ Khái niệm Cost trong Cơ sở Dữ liệu

⬅️ **[[MOC - Query Optimization]]** | 🔗 **[[MOC - Database Overview]]**

---

## 1. Định nghĩa

**Cost (Chi phí)** là một giá trị số không thứ nguyên do **[[SQL Optimizer]]** tính toán, đại diện cho **tổng tài nguyên ước tính** (CPU Cycles + Đĩa I/O) mà hệ thống cần tiêu tốn để hoàn thành một chiến lược thực thi cụ thể.

Khi nhận một câu lệnh SQL phức tạp, Optimizer có thể sinh ra hàng chục kế hoạch thực thi khác nhau. Thuật toán **Cost-Based Optimizer (CBO)** sẽ tính Cost cho từng phương án và luôn chọn ra phương án có **Cost thấp nhất** để tạo thành **[[Execution Plan]]**.

---

## 2. Công thức Tổng quát của Cost

Về bản chất, hàm tính Cost của hầu hết RDBMS hiện đại dựa trên mô hình:

$$	ext{Cost} = (	ext{Số lượng Block I/O} 	imes W_{io}) + (	ext{Số chu kỳ CPU} 	imes W_{cpu})$$

Trong đó:
- **I/O Cost:** Số lượng [[Block (Page)]] cần nạp từ Ổ đĩa vào [[Buffer Cache]]. Đọc ngẫu nhiên (Random I/O) có trọng số chi phí cao hơn nhiều so với đọc tuần tự (Sequential I/O).
- **CPU Cost:** Số chu kỳ CPU cần để thực hiện các phép so sánh (`WHERE`), phép ghép chuỗi, tính toán hàm toán học, và sắp xếp dữ liệu (`ORDER BY`, `GROUP BY`, `SORT MERGE`).

---

## 3. Bản chất Thực chiến: Cost Thấp nhất Chưa chắc đã là Nhanh nhất!

> [!WARNING]
> Cost là một con số **ước lượng lý thuyết** dựa trên **[[Statistics (Thống kê Database)]]**, không phải là thời gian chạy thực tế bằng đồng hồ bấm giờ (Wall-clock Time).

### Tại sao có trường hợp Cost thấp nhưng chạy lại rất chậm?
1. **Thống kê bị cũ (Stale Statistics):** Bảng có 20 triệu dòng nhưng Statistic lưu là 100 dòng. Optimizer tính toán thấy dùng `[[Nested Loop Join]]` có Cost cực rẻ (vì nghĩ chỉ lặp 100 lần), nhưng khi chạy thật thì lặp 20 triệu lần làm treo server! (Xem: **[[Case - Hai bảng giống nhau nhưng hiệu năng khác nhau]]**).
2. **Độ phân tán dữ liệu bị lệch (Data Skew):** Cột `Status = 'Pending'` chỉ có 10 dòng, nhưng `Status = 'Completed'` có 10 triệu dòng. Nếu không có Histogram, Optimizer sẽ tính Cost trung bình và chọn sai phương án cho giá trị 'Completed'.

---

## 🔗 Liên kết Mở rộng
- Khái niệm liên quan: [[SQL Optimizer]], [[Execution Plan]], [[Statistics (Thống kê Database)]], [[Block (Page)]]
- Nguyên lý & Thực chiến: [[Nguyên lý 3+2 trong Database]], [[Tư duy tối ưu Database (Database Tuning Mindset)]], [[Tại sao Database không chọn Index (Bản chất Cost-Based Optimizer)]]
