---
tags:
  - dsa
  - big-o
  - constant-time
stage: 1
type: big-o
status: completed
created: 2026-08-24
updated: 2026-08-27
aliases:
  - O(1)
  - Constant Time
  - Thời gian hằng số
---

# 🟢 O(1) - Constant Time (Thời Gian Hằng Số)

> [[00 - Master Dashboard|🧭 Dashboard]] / [[Master MOC|🗺️ Master MOC]] / [[Big-O Notation - MOC|⚡ Big-O MOC]]

---

## 1. Bản Chất Cốt Lõi (Mental Model)
Dù dữ liệu của bạn có phình to từ 10 bản ghi lên 10 tỷ bản ghi, thời gian xử lý vẫn **giữ nguyên tuyệt đối không đổi** (chỉ tốn đúng 1 thao tác tính toán).

> [!TIP]
> **Hình dung sinh động:** Giống như việc bạn bấm công tắc điện trong phòng — dù căn phòng rộng 10m² hay một nhà thi đấu khổng lồ 10.000m², bóng đèn vẫn bật sáng ngay lập tức chỉ với 1 cái chạm tay.

---

## 2. Dấu Hiệu Nhận Biết (Code Triggers)
- Truy cập trực tiếp phần tử qua chỉ số Index: `arr[5]`.
- Truy xuất hoặc gán phần tử trong bảng băm qua Key: `map["user_id"]`.
- Thao tác gán biến, phép toán số học cơ bản: `a + b`, `x = y * 2`.
- Các câu lệnh điều kiện `if-else` đơn lẻ không chứa vòng lặp phụ thuộc vào kích thước dữ liệu $n$.

---

## 3. Cấu Trúc Dữ Liệu & Thao Tác Liên Quan
- [[Array & Dynamic Array|Mảng (Arrays)]]: Truy cập ngẫu nhiên qua Index `arr[i]`.
- [[Hash Table & HashSet|Bảng băm & Tập hợp băm]]: Tra cứu, chèn, xóa phần tử trung bình (Average Case).
- [[Stack|Ngăn xếp (Stack)]] & [[Queue & Deque|Hàng đợi (Queue)]]: Thao tác thêm/xóa ở đầu hoặc đỉnh (`push`, `pop`, `enqueue`, `dequeue`).
- [[Linked List|Danh sách liên kết]]: Chèn/xóa node tại vị trí đầu (`Head`) hoặc vị trí con trỏ đã biết trước.

---

## 4. Cách Tối Ưu Thực Tế (Architect's View)
- **Đỉnh cao của tối ưu hóa:** $O(1)$ là "chén thánh" mà mọi kiến trúc sư hệ thống đều hướng tới khi thiết kế tầng lưu trữ và xử lý dữ liệu.
- **Ứng dụng thực chiến:** Khi một chức năng tra cứu bị nghẽn cổ chai ở mức $O(n)$ do duyệt qua danh sách, ta áp dụng kỹ thuật **Đánh đổi RAM lấy Tốc độ**: Ép dữ liệu vào một [[Hash Table & HashSet|Hash Table]] hoặc bộ nhớ đệm [[LRU Cache|LRU Cache]] để đưa thao tác tra cứu về $O(1)$.

---

## 🧠 Thẻ Ghi Nhớ Nhanh (Spaced Repetition)
Tại sao truy xuất mảng qua index lại đạt $O(1)$? #card
?
Vì các ô nhớ trong mảng nằm liên tiếp nhau (contiguous memory). Máy tính chỉ cần tính toán địa chỉ bộ nhớ theo công thức: $\text{Địa chỉ} = \text{Địa chỉ gốc} + (\text{index} \times \text{kích thước ô nhớ})$ với đúng 1 phép toán số học duy nhất.
Nêu 3 cấu trúc dữ liệu cho phép truy xuất/thêm phần tử trong $O(1)$? #card
?
1. [[Array & Dynamic Array|Array]] (truy xuất qua index).
2. [[Hash Table & HashSet|Hash Table]] (tra cứu key-value trung bình).
3. [[Stack|Stack]] / [[Queue & Deque|Queue]] (thêm/xóa ở đỉnh hoặc đầu danh sách).
