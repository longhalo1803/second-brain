---
tags:
  - dsa
  - data-structure
  - linear
stage: 2
type: data-structure
status: completed
created: 2026-08-27
updated: 2026-08-27
aliases:
  - Queue
  - Deque
  - Double-ended Queue
  - Hàng đợi
  - Queues
---

# 🚶 Hàng Đợi & Hàng Đợi Hai Đầu (Queue & Deque)

> [[00 - Master Dashboard|🧭 Dashboard]] / [[Master MOC|🗺️ Master MOC]] / [[Roadmap|📋 Roadmap]]

---

## 1. Bản Chất Cốt Lõi (Mental Model)
- **Queue (Hàng đợi chuẩn):** Hoạt động theo quy tắc **FIFO (First In, First Out)** — Ai đến trước được phục vụ trước. Thêm vào cuối (`enqueue`), lấy ra ở đầu (`dequeue`) đều đạt [[O(1) - Constant Time\|$O(1)$]].
- **Deque (Double-Ended Queue):** Hàng đợi hai đầu linh hoạt, cho phép thêm và xóa phần tử ở **cả 2 đầu** (Front & Rear) trong [[O(1) - Constant Time\|$O(1)$]].
- **Hình dung:** Giống như hàng người xếp hàng mua vé xem phim. Người đứng đầu hàng mua vé xong đi vào rạp, người mới đến phải đứng vào cuối hàng.

---

## 2. Bảng Độ Phức Tạp

| Thao Tác | Queue Chuẩn | Deque (2 đầu) |
| :--- | :--- | :--- |
| **Thêm ở đầu (Push Front)** | ❌ Không hỗ trợ | [[O(1) - Constant Time\|$O(1)$]] |
| **Thêm ở cuối (Push Back / Enqueue)** | [[O(1) - Constant Time\|$O(1)$]] | [[O(1) - Constant Time\|$O(1)$]] |
| **Xóa ở đầu (Pop Front / Dequeue)** | [[O(1) - Constant Time\|$O(1)$]] | [[O(1) - Constant Time\|$O(1)$]] |
| **Xóa ở cuối (Pop Back)** | ❌ Không hỗ trợ | [[O(1) - Constant Time\|$O(1)$]] |

---

## 3. Ứng Dụng Thực Tế & Thiết Kế Hệ Thống
- **Message Queues / Task Scheduling:** RabbitMQ, Kafka, AWS SQS, Hàng đợi lệnh in ấn máy in, Hàng đợi Request của Web Server (Nginx).
- **Thuật toán Duyệt Đồ Thị theo chiều rộng ([[Graph Representations & Traversal|BFS - Breadth First Search]]):** Tìm đường đi ngắn nhất giữa hai điểm.
- **Kỹ thuật Cửa sổ trượt nâng cao ([[Sliding Window Pattern]]):** Dùng Deque đơn điệu (Monotonic Deque) để tìm phần tử Max/Min trong cửa sổ trượt kích thước $K$ trong [[O(n) - Linear Time|$O(n)$]].

---

## 🧠 Thẻ Ghi Nhớ Nhanh (Spaced Repetition)
Quy tắc cốt lõi của Queue là gì và sự khác biệt với Deque? #card
?
- **Queue:** Quy tắc **FIFO (First In, First Out)**, chỉ thêm ở cuối và lấy ở đầu ($O(1)$).
- **Deque:** Cho phép cả `push_front`, `push_back`, `pop_front`, `pop_back` đều trong $O(1)$.
Thuật toán duyệt đồ thị nào bắt buộc phải dùng Queue? #card
?
**BFS (Breadth-First Search - Duyệt theo chiều rộng)** để tìm đường đi ngắn nhất không trọng số.
