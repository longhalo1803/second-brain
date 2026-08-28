---
tags:
  - dsa
  - pattern
  - stack
  - monotonic-stack
stage: 5
type: pattern
status: completed
created: 2026-08-27
updated: 2026-08-27
aliases:
  - Monotonic Stack
  - Ngăn xếp đơn điệu
  - Monotonic Stack Pattern
---

# 🥞 Kỹ Thuật Ngăn Xếp Đơn Điệu (Monotonic Stack Pattern)

> [[00 - Master Dashboard|🧭 Dashboard]] / [[Master MOC|🗺️ Master MOC]] / [[Roadmap|📋 Roadmap]]

---

## 1. Bản Chất Cốt Lõi (Mental Model)
- **Mục tiêu:** Tìm **"Phần tử lớn hơn gần nhất" (Next Greater Element)** hoặc **"Phần tử nhỏ hơn gần nhất"** cho mọi phần tử trong mảng trong thời gian [[O(n) - Linear Time\|$O(n)$]] thay vì $O(n^2)$.
- **Nguyên lý:** Duy trì các phần tử trong [[Stack]] theo một thứ tự đơn điệu nghiêm ngặt (luôn tăng dần hoặc luôn giảm dần).
- **Hành động khi có phần tử mới:** Pop toàn bộ các phần tử ở đỉnh Stack vi phạm tính chất đơn điệu trước khi push phần tử mới vào. Mỗi phần tử bị pop ra chính là lúc ta tìm thấy phần tử lớn hơn/nhỏ hơn gần nhất của nó.

---

## 2. Các Bài Toán Kinh Điển
- **Next Greater Element I & II:** Tìm số lớn hơn tiếp theo trong mảng tròn.
- **Daily Temperatures:** Đếm số ngày phải chờ đến ngày có nhiệt độ cao hơn.
- **Largest Rectangle in Histogram:** Tìm hình chữ nhật lớn nhất trong biểu đồ cột.
- **Trapping Rain Water:** Tính lượng nước mưa đọng lại giữa các cột.
