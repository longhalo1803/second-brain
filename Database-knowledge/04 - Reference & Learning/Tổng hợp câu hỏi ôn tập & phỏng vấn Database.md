---
title: Tổng hợp Câu hỏi Ôn tập & Phỏng vấn Chuyên sâu về Database
aliases:
  - Tổng hợp các câu hỏi
  - Tổng hợp câu hỏi ôn tập & phỏng vấn Database
  - Database Interview Questions
  - Câu hỏi phỏng vấn Database
tags:
  - database
  - interview
  - qna
  - index
  - performance
  - review
type: reference
created: 2026-06-25
updated: 2026-08-26
---

# 💡 Tổng hợp Câu hỏi Ôn tập & Phỏng vấn Chuyên sâu về Database

⬅️ **[[MOC - Database Overview]]** | 🔗 **[[Lộ trình học Database toàn diện cho Developer]]**

---

## 📌 PHẦN 1: BẢN CHẤT VẬT LÝ VÀ ĐƠN VỊ LƯU TRỮ

### Câu hỏi 1: Tại sao nói Database không bao giờ làm việc với đơn vị Bản ghi (Record / Row)?
- **Trả lời:** Đơn vị đọc/ghi (I/O) vật lý nhỏ nhất của mọi Database là **[[Block (Page)]]** (thường là 8KB - 16KB).
- Dù bạn chỉ muốn lấy 1 dòng dữ liệu, Database bắt buộc phải nạp nguyên vẹn toàn bộ Block chứa dòng đó từ Ổ đĩa vào [[Buffer Cache]] trên RAM.
- Do đó, hiệu năng câu lệnh phụ thuộc vào **tổng số lượng Block cần quét**, chứ không phụ thuộc vào số lượng Row trả về.

---

### Câu hỏi 2: Làm sao để tìm một bản ghi trong bảng hàng chục triệu dòng bằng Index?
- **Trả lời:** Dựa trên 2 nguyên lý cốt lõi:
  1. **Dữ liệu trong Index luôn được sắp xếp theo thứ tự (Sorted).**
  2. **Index luôn lưu kèm con trỏ tọa độ vật lý (Row ID / Pointer)** trỏ thẳng tới Block chứa bản ghi gốc.
- Database chỉ cần tra mục lục Index để lấy tọa độ rồi "nhảy dù" thẳng vào đúng Block trên đĩa, bỏ qua hàng triệu bản ghi không liên quan.

---

## 📌 PHẦN 2: CẤU TRÚC VẬT LÝ BÊN TRONG CỦA B-TREE INDEX

### Câu hỏi 3: Cấu trúc vật lý của Index được tổ chức ra sao để tìm kiếm siêu tốc?
- **Trả lời:** Index là sự kết hợp hoàn hảo của 2 cấu trúc dữ liệu:
  1. **Cây cân bằng (B-Tree) - Đóng vai trò "Hạ cánh thẳng đứng":** Đi từ Gốc (Root) -> Nhánh (Branch) -> Lá (Leaf). Độ sâu chỉ 3 - 4 tầng, giúp tìm trúng Nút lá chứa bản ghi đầu tiên trong vài tích tắc.
  2. **Danh sách liên kết đôi (Doubly Linked List) - Đóng vai trò "Quét ngang":** Tại tầng Nút lá, các trang Index móc nối với nhau 2 chiều. Vì dữ liệu đã sắp xếp sẵn, Database chỉ cần trượt ngang để gom toàn bộ các dòng thỏa mãn điều kiện.

---

### Câu hỏi 4: Trình tự thực thi chính xác của một câu lệnh khi dùng Index là gì? Điểm nghẽn nằm ở đâu?
- **Trả lời:** Quá trình diễn ra qua 3 bước:
  - **Bước 1: Duyệt cây B-Tree:** Rơi từ Gốc xuống Lá (Luôn luôn cực nhanh).
  - **Bước 2: Quét danh sách liên kết đôi:** Trượt ngang gom Row ID. *(Có thể chậm nếu điều kiện lọc trả về quá nhiều dòng - Low Selectivity).*
  - **Bước 3: Truy cập ngược lại bảng gốc (Table Access by RowID):** Dùng Row ID nhảy vào ổ cứng lấy nốt các cột còn thiếu.
- > [!CAUTION]
  > **Sát thủ Random I/O:** Bước 3 là thao tác chậm nhất thế giới database nếu phải nhảy ngẫu nhiên hàng trăm nghìn lần vào ổ đĩa.
- **💡 Giải pháp:** Sử dụng **Covering Index (Index Bao phủ)** - đưa toàn bộ các cột cần lấy vào Index để triệt tiêu hoàn toàn Bước 3!

---

## 📌 PHẦN 3: CÁC HIỂU LẦM TAI HẠI NHẤT TRONG PHỎNG VẤN

### Câu hỏi 5: Có phải cứ bảng dữ liệu lớn thì dùng Index chắc chắn sẽ chạy nhanh hơn?
- **Trả lời:** **SAI.** Nếu câu lệnh lọc lấy ra lượng lớn dữ liệu (> 15% - 20% bảng), chi phí Random I/O của Index sẽ cực lớn. Lúc này, **[[SQL Optimizer]]** sẽ từ chối Index và chuyển sang **[[Full Table Scan]]** (Multi-block Sequential Read) để quét nhanh hơn (Xem: **[[Case - Khi nào Index phản tác dụng (Ô tô tải vs Xe máy)]]**).

---

### Câu hỏi 6: Khi Server mất điện đột ngột, Database có phải xây dựng lại Index từ đầu không?
- **Trả lời:** **SAI.** Cây Index được lưu trữ cố định trên **Ổ đĩa vật lý (Data Files)** giống hệt như các bảng dữ liệu gốc, không phải chỉ nằm trên RAM. Khi server khởi động lại, Database chỉ việc nạp lại các Block của Index lên RAM để dùng tiếp.

---

### Câu hỏi 7: Khi bảng gốc liên tục Thêm/Sửa/Xóa (DML) làm dữ liệu lộn xộn, Index có tìm đúng không?
- **Trả lời:** **VẪN TÌM CHÍNH XÁC.** Index là một hệ thống định vị độc lập. Mỗi khi có thao tác DML ở bảng gốc, Database tự động cập nhật lại các nút lá của cây B-Tree và trỏ lại Row ID tương ứng.

---

### Câu hỏi 8: Tại sao bảng 0 bản ghi nhưng câu lệnh `SELECT *` vẫn chạy mất hàng giây?
- **Trả lời:** Do người dùng dùng lệnh `DELETE` thay vì `TRUNCATE`. Các dòng bị xóa nhưng hàng trăm nghìn **[[Block (Page)]]** rỗng và mốc **High Water Mark** vẫn còn nguyên. Câu lệnh `SELECT *` buộc phải dùng **[[Full Table Scan]]** quét qua toàn bộ các Block rỗng này (Xem: **[[Case - Table 0 row nhưng truy vấn vẫn cực chậm]]**).

---

### Câu hỏi 9: Tại sao cột đã đánh Index nhưng Optimizer vẫn chọn Full Table Scan? Dùng Hint ép Index có nên không?
- **Trả lời:** 
  - **Lý do Optimizer từ chối Index:** Optimizer hiện đại sử dụng mô hình **Cost-Based Optimizer (CBO)**, tính toán chi phí $\text{Cost} = f(\text{Block I/O}, \text{CPU})$. Khi dữ liệu trả về chiếm số lượng lớn, việc duyệt qua Index rồi nhảy Random I/O về bảng gốc (**Table Access by RowID**) sẽ làm số lượng Block I/O tăng vọt gấp hàng chục lần so với quét tuần tự (**[[Full Table Scan]]**).
  - **Có nên dùng Hint ép Index?** **HẦU HẾT LÀ KHÔNG NÊN trong Production.** Thực nghiệm trên Oracle và SQL Server chứng minh khi dùng Hint ép Index, số lượng Logical Reads tăng từ 44.000 pages lên **3 triệu pages** (tăng 70 lần), Consistent Gets từ 1.4 triệu lên **24 triệu blocks** (tăng 17 lần), làm nghẽn I/O đĩa trầm trọng (Xem: **[[Tại sao Database không chọn Index (Bản chất Cost-Based Optimizer)]]**).

---

### Câu hỏi 10: Tại sao câu lệnh có `ORDER BY` theo cột đã có Index nhưng Optimizer lại chọn Full Table Scan + Thao tác SORT?
- **Trả lời:**
  - Index lưu dữ liệu đã sắp xếp sẵn. Nếu quét theo Index, Database **loại bỏ được bước SORT**.
  - Tuy nhiên, để lấy các cột còn lại cho mỗi bản ghi, Database phải thực hiện hàng triệu lần Table Access by RowID (Random I/O).
  - Optimizer so sánh và nhận thấy: **Chi phí CPU để thực hiện thuật toán Sort trong bộ nhớ RAM (Cost = 86k) rẻ hơn rất nhiều so với chi phí Random I/O khi duyệt theo Index (Cost = 1.000.000+)**. Do đó, Optimizer quyết định quét Full bảng rồi mới Sort (Xem chi tiết tại: **[[Tại sao Database không chọn Index (Bản chất Cost-Based Optimizer)]]**).

---

## 🔗 Liên kết Điều hướng
- Bản đồ tổng quan: [[MOC - Database Overview]]
- Khái niệm liên quan: [[Index]], [[Block (Page)]], [[Execution Plan]], [[SQL Optimizer]], [[Cost]], [[Tại sao Database không chọn Index (Bản chất Cost-Based Optimizer)]]
