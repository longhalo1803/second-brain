---
title: Buffer Cache trong Database (Bộ nhớ Đệm Dữ liệu RAM)
aliases:
  - Buffer Cache
  - Database Buffer Cache
  - Buffer Pool
  - Cache
  - Memory Cache
tags:
  - database
  - memory
  - architecture
  - performance
  - core-concept
type: concept
created: 2026-06-18
updated: 2026-08-26
---

# ⚡ Khái niệm Buffer Cache / Buffer Pool

⬅️ **[[MOC - Storage & Engine]]** | 🔗 **[[MOC - Database Overview]]**

---

## 1. Định nghĩa

**Buffer Cache** (trong Oracle/Postgres) hay **Buffer Pool** (trong MySQL InnoDB / SQL Server) là một vùng bộ nhớ RAM chuyên dụng trong [[Database Instance]], được thiết kế để lưu trữ tạm thời các [[Block (Page)]] dữ liệu được đọc lên từ Ổ đĩa (Disk).

![[Pasted image 20260618113050.png]]

![[Pasted image 20260618113055.png]]

---

## 2. Vì sao Buffer Cache là Trái tim của Hiệu năng Database?

Tốc độ truy xuất giữa RAM và Ổ đĩa (kể cả SSD NVMe hiện đại nhất) có sự chênh lệch hàng nghìn lần:

| Thiết bị Lưu trữ | Độ trễ Truy xuất (Latency) | Tương quan Tốc độ |
| :--- | :--- | :--- |
| **RAM (Buffer Cache)** | ~ 10 - 100 nano-giây (ns) | Nhanh gấp ~1.000 - 10.000 lần |
| **SSD NVMe (Flash)** | ~ 50 - 150 micro-giây ($\mu$s) | Nhanh trung bình |
| **HDD (Quay cơ học)** | ~ 5 - 10 mili-giây (ms) | Rất chậm (Nút thắt cổ chai) |

Khi một câu lệnh SQL yêu cầu dữ liệu:
1. **Logical Read (Buffer Hit):** Database tìm thấy Block mong muốn đã nằm sẵn trên Buffer Cache. Dữ liệu được trả về ngay lập tức với tốc độ RAM (Microseconds).
2. **Physical Read (Buffer Miss):** Block chưa có trên RAM. Database phải phát tín hiệu I/O đọc Block từ Ổ đĩa nạp vào Buffer Cache rồi mới xử lý tiếp (Milliseconds).

---

## 3. Thuật toán Quản lý & Thay thế Trang (LRU Algorithm)

Vì dung lượng RAM luôn có hạn trong khi dung lượng ổ đĩa ngày càng phình to, Buffer Cache sử dụng thuật toán **LRU (Least Recently Used)** hoặc biến thể **Clock Sweep / 2Q**:

```
+--------------------------------------------------------------+
|                   BUFFER CACHE (LRU LIST)                    |
|  [ MRU End ] <------------------------------> [ LRU End ]    |
|   (Mới dùng)                                   (Ít dùng)     |
|   Block A   |   Block B   |   Block C   | ... | Block Z (Bị xóa)|
+--------------------------------------------------------------+
```

- **MRU (Most Recently Used):** Các Block vừa được truy vấn sẽ được đẩy lên đầu danh sách.
- **LRU (Least Recently Used):** Các Block lâu ngày không ai đụng tới sẽ bị dạt dần về cuối danh sách. Khi RAM hết chỗ, các Block ở đuôi LRU sẽ bị giải phóng (Evict) để nhường chỗ cho Block mới.
- **Dirty Blocks (Khối dữ liệu bị sửa đổi):** Khi bạn chạy lệnh `UPDATE`, dữ liệu được sửa ngay trên RAM (gọi là Dirty Block). Tiến trình nền **DBWn (Database Writer)** hoặc **Checkpointer** sẽ định kỳ ghi gom các Dirty Block này xuống ổ đĩa vật lý.

---

## 4. Tác động của Buffer Cache đến Tối ưu hóa Truy vấn

1. **Hiệu ứng "Lần đầu chậm, lần hai nhanh":** Lần đầu chạy câu lệnh phải tốn Physical I/O (chậm). Lần thứ hai toàn bộ Block đã nằm trên Buffer Cache nên chỉ tốn Logical I/O (nhanh).
2. **Thảm họa quét bảng lớn (Cache Pollution):** Nếu chạy một câu lệnh `SELECT *` quét full một bảng 50GB trên server RAM 32GB, toàn bộ các dữ liệu quan trọng đang nằm trên Cache sẽ bị cuốn trôi (Evict) sạch sẽ để nhường chỗ cho bảng to, làm toàn bộ hệ thống bị chậm dây chuyền.

---

## 🔗 Liên kết Liên quan
- Khái niệm liên quan: [[Block (Page)]], [[Database Instance]], [[Cost]], [[Execution Plan]]
- Nguyên lý ứng dụng: [[Nguyên lý 3+2 trong Database]], [[3 Yếu tố cốt lõi làm Database nhanh]]
