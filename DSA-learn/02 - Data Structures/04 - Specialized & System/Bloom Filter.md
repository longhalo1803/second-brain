---
tags:
  - dsa
  - data-structure
  - system-design
  - probabilistic
stage: 6
type: data-structure
status: completed
created: 2026-08-27
updated: 2026-08-27
aliases:
  - Bloom Filter
  - Bộ lọc Bloom
---

# 🌸 Bộ Lọc Bloom (Bloom Filter)

> [[00 - Master Dashboard|🧭 Dashboard]] / [[Master MOC|🗺️ Master MOC]] / [[Roadmap|📋 Roadmap]]

---

## 1. Bản Chất Cốt Lõi (Mental Model)
- **Định nghĩa:** Là một cấu trúc dữ liệu xác suất (Probabilistic Data Structure) sử dụng một mảng bit (Bit Array) và $k$ hàm băm độc lập để kiểm tra xem **một phần tử có thuộc một tập hợp hay không** với dung lượng RAM siêu nhỏ.
- **Quy tắc trả lời dị thường:**
  - ❌ **"KHÔNG (False)":** Chính xác $100\%$ — Phần tử chắc chắn chưa bao giờ được thêm vào tập hợp.
  - ⚠️ **"CÓ (True)":** Có thể đúng hoặc là **Dương tính giả (False Positive)** — Có một xác suất nhỏ phần tử chưa được thêm vào nhưng các bit ngẫu nhiên bị trùng.
  - 🚫 **Không bao giờ có Âm tính giả (False Negative):** Nếu phần tử đã thêm thì chắc chắn filter sẽ báo Có.

---

## 2. Bảng Độ Phức Tạp & Bộ Nhớ

| Thao Tác | Độ Phức Tạp Thời Gian | Không Gian Bộ Nhớ (Space) |
| :--- | :--- | :--- |
| **Thêm phần tử (Insert)** | $O(k)$ ($k$ hàm băm $\approx O(1)$) | Chỉ tốn vài bit cho mỗi phần tử |
| **Kiểm tra tồn tại (Query)** | $O(k)$ ($k$ hàm băm $\approx O(1)$) | Độc lập với độ dài của dữ liệu gốc |
| **Xóa phần tử (Delete)** | ❌ Không hỗ trợ (vì sẽ làm sai lệch bit của phần tử khác) | Cần biến thể Counting Bloom Filter |

---

## 3. Ứng Dụng Thực Tế Trong Các Hệ Thống Lớn (Big Tech)
- **Tránh Cache Penetration & Lãng phí Disk I/O:** Trong Cassandra, HBase, RocksDB — Bloom Filter kiểm tra trước xem một Row Key có nằm trong file SSTable trên ổ cứng không trước khi đọc đĩa. Nếu Bloom Filter báo KHÔNG, bỏ qua ngay ổ đĩa.
- **Trình duyệt Google Chrome:** Kiểm tra URL độc hại. Chrome giữ một Bloom Filter vài MB trên máy người dùng để kiểm tra ngay lập tức, chỉ gửi request lên máy chủ Google khi có cảnh báo "Có".
- **Kiểm tra Tên Người Dùng / Email tồn tại (Username Availability):** Kiểm tra tức thì 1 tỷ username mà chỉ tốn vài chục MB RAM.

---

## 🧠 Thẻ Ghi Nhớ Nhanh (Spaced Repetition)
Câu trả lời "KHÔNG" của Bloom Filter có độ tin cậy bao nhiêu phần trăm? #card
?
**Chính xác 100%**. Nếu Bloom Filter trả lời "Không", phần tử đó chắc chắn không tồn tại trong tập dữ liệu.
Tại sao hệ cơ sở dữ liệu phân tán (Cassandra, RocksDB) luôn đặt Bloom Filter ở trước ổ đĩa? #card
?
Để **tiết kiệm I/O đọc đĩa tốn kém**. Nếu Bloom Filter xác nhận dữ liệu không có trong file, DB không cần tốn công đọc từ ổ đĩa cứng.
