---
title: Database Instance (Kiến trúc Bộ nhớ & Tiến trình Nền)
aliases:
  - Database Instance
  - Instance
  - Kiến trúc Instance
  - Database Architecture
tags:
  - database
  - architecture
  - memory
  - core-concept
type: concept
created: 2026-06-18
updated: 2026-08-26
---

# 🏛️ Khái niệm Database Instance trong RDBMS

⬅️ **[[MOC - Storage & Engine]]** | 🔗 **[[MOC - Database Overview]]**

---

## 1. Phân biệt Database và Instance

Rất nhiều kỹ sư nhầm lẫn hai khái niệm này:
- **Database (Cơ sở dữ liệu):** Là tập hợp các **tập tin vật lý lưu trữ trên ổ đĩa (Disk Files)** bao gồm Data Files (chứa các [[Block (Page)]]), Redo Log Files/WAL Files, Control Files.
- **Instance (Thực thể xử lý):** Là tập hợp các **cấu trúc bộ nhớ trên RAM** và các **tiến trình nền (Background Processes)** chạy trên hệ điều hành để quản lý và truy xuất vào Database.

```
+-------------------------------------------------------------+
|                      DATABASE INSTANCE (RAM)                |
|  [ Buffer Cache ]  [ Shared Pool / Plan Cache ]  [ Redo Buffer ] |
|  [ DBWn (Writer) ] [ LGWR (Log Writer) ] [ CKPT (Checkpoint)]  |
+-------------------------------------------------------------+
                              ↕ (I/O)
+-------------------------------------------------------------+
|                      DATABASE FILES (DISK)                  |
|  [ Data Files (*.dbf / *.ibd) ]  [ Redo / WAL Logs ]         |
+-------------------------------------------------------------+
```

---

## 2. Các Thành phần Bộ nhớ Cốt lõi trên RAM

1. **[[Buffer Cache]] (Buffer Pool):** Lưu trữ các khối dữ liệu (Data Blocks) để phục vụ đọc/ghi với tốc độ RAM.
2. **Shared Pool / Plan Cache:** Lưu trữ các câu lệnh SQL đã phân tích cú pháp và các **[[Execution Plan]]** tái sử dụng để phục vụ **Soft Parse** (Xem: **[[Quy trình 6 bước xử lý câu lệnh SQL]]**).
3. **Redo Log Buffer / WAL Buffer:** Vùng đệm chứa các bản ghi nhật ký thay đổi trước khi được ghi an toàn xuống ổ đĩa.
4. **PGA (Program Global Area / Work Memory):** Vùng nhớ riêng cho từng User Session để thực hiện Sort, Hash Join, Bitmap Merge.

---

## 3. Các Tiến trình Nền Trọng yếu (Background Processes)

- **DBWn (Database Writer):** Chịu trách nhiệm gom các Dirty Blocks từ Buffer Cache ghi xuống Data Files trên ổ đĩa.
- **LGWR (Log Writer) / WAL Writer:** Ghi các thay đổi từ Redo Buffer xuống file nhật ký ngay khi người dùng gõ lệnh `COMMIT`.
- **CKPT (Checkpoint Process):** Cập nhật đồng bộ thông tin Header của các file dữ liệu, đánh dấu mốc phục hồi an toàn khi gặp sự cố mất điện.
- **SMON / PMON:** Tự động khôi phục Instance khi crash, dọn dẹp tài nguyên và giải phóng Lock của các session bị ngắt kết nối đột ngột.

---

## 🔗 Liên kết Mở rộng
- Khái niệm liên quan: [[Buffer Cache]], [[Block (Page)]], [[Execution Plan]], [[Transaction & MVCC]]
- Nguyên lý: [[Nguyên lý 3+2 trong Database]], [[Quy trình 6 bước xử lý câu lệnh SQL]]
