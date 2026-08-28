---
title: Execution Plan trong Database (Kế hoạch Thực thi SQL)
aliases:
  - Execution Plan
  - Kế hoạch thực thi
  - Explain Plan
  - Chiến lược thực thi
  - SQL Execution Plan
tags:
  - database
  - sql-tuning
  - optimizer
  - performance
  - core-concept
type: concept
created: 2026-06-16
updated: 2026-08-26
---

# 🗺️ Khái niệm Execution Plan (Kế hoạch Thực thi SQL)

⬅️ **[[MOC - Query Optimization]]** | 🔗 **[[MOC - Database Overview]]**

---

## 1. Định nghĩa

**Execution Plan (Kế hoạch thực thi)** là bản đồ chỉ đường chi tiết do **[[SQL Optimizer]]** tự động sinh ra, mô tả chính xác từng thao tác tuần tự mà Database Engine sẽ thực hiện để lấy dữ liệu cho một câu lệnh SQL.

SQL là một ngôn ngữ **khai báo (Declarative Language)**: Bạn chỉ nói cho Database biết bạn *muốn lấy cái gì* (`SELECT ... FROM ... WHERE ...`), chứ không ra lệnh *lấy như thế nào*. Execution Plan chính là câu trả lời của Database cho câu hỏi *lấy như thế nào*.

![[Pasted image 20260616161013.png]]

---

## 2. Cấu trúc của một Execution Plan

Một Execution Plan chuẩn thường có dạng **Cây thực thi (Execution Tree)** hoặc bảng phân cấp phân tầng, bao gồm các thông số cốt lõi:

```sql
--------------------------------------------------------------------------------------------------
| Id  | Operation                     | Name          | Rows  | Bytes | Cost (%CPU)| Time        |
--------------------------------------------------------------------------------------------------
|   0 | SELECT STATEMENT              |               |     1 |    45 |     3   (0)| 00:00:00.01 |
|   1 |  TABLE ACCESS BY INDEX ROWID  | CUSTOMERS     |     1 |    45 |     3   (0)| 00:00:00.01 |
|*  2 |   INDEX UNIQUE SCAN           | PK_CUSTOMERS  |     1 |       |     2   (0)| 00:00:00.01 |
--------------------------------------------------------------------------------------------------
```

### Các Thành phần Trọng yếu:
1. **Operation (Thao tác):** Cách thức Database đọc dữ liệu ([[Data Access Methods]]) hoặc cách kết nối các bảng ([[Join Methods]]).
   - Ví dụ: `TABLE ACCESS FULL`, `INDEX RANGE SCAN`, `NESTED LOOPS`, `HASH JOIN`.
2. **Rows (Cardinality):** Số lượng bản ghi ước tính mà thao tác đó sẽ trả về (dựa trên [[Statistics (Thống kê Database)]]).
3. **Cost:** Điểm chi phí ước tính (CPU + I/O) do Optimizer tính toán (Xem: **[[Cost]]**).
4. **Predicate Information (Điều kiện lọc):**
   - **Access Predicate:** Điều kiện dùng để nhảy trực tiếp vào Index.
   - **Filter Predicate:** Điều kiện lọc sau khi đã đọc dữ liệu lên RAM.

---

## 3. Nguyên tắc Đọc Execution Plan

> [!TIP]
> **Quy tắc Vàng khi đọc Plan:** Đọc từ **Trong ra Ngoài** (Indent sâu nhất đọc trước) và từ **Trên xuống Dưới** (Cùng cấp Indent thì dòng trên chạy trước).

---

## 4. Tại sao Phân tích Execution Plan là Kỹ năng Sống còn của Dev & DBA?

- **Phát hiện Index bị bỏ qua:** Có Index nhưng Plan lại hiển thị `TABLE ACCESS FULL`.
- **Nhận diện sai lệch Thống kê:** Bảng thực tế có 10 triệu dòng nhưng Plan ước tính `Rows = 1`.
- **Xác định điểm nghẽn (Bottlenecks):** Tìm ra bước nào trong cây thực thi chiếm 90% tổng thời gian (Cost cao nhất).

---

## 🔗 Liên kết & Khái niệm Mở rộng
- Khái niệm liên quan: [[SQL Optimizer]], [[Cost]], [[Data Access Methods]], [[Join Methods]], [[Statistics (Thống kê Database)]]
- Nguyên lý: [[Quy trình 6 bước xử lý câu lệnh SQL]], [[Tư duy tối ưu Database (Database Tuning Mindset)]]
