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
  - Stack
  - Stacks
  - Ngăn xếp
---

# 🥞 Ngăn Xếp (Stack)

> [[00 - Master Dashboard|🧭 Dashboard]] / [[Master MOC|🗺️ Master MOC]] / [[Roadmap|📋 Roadmap]]

---

## 1. Bản Chất Cốt Lõi (Mental Model)
- **Quy tắc:** **LIFO (Last In, First Out)** — Phần tử nào được đưa vào sau cùng sẽ được lấy ra đầu tiên.
- **Thao tác chính:**
  - `push(x)`: Đặt phần tử lên đỉnh (Top) $\to$ [[O(1) - Constant Time\|$O(1)$]].
  - `pop()`: Lấy và xóa phần tử ở đỉnh (Top) $\to$ [[O(1) - Constant Time\|$O(1)$]].
  - `peek() / top()`: Xem phần tử ở đỉnh mà không xóa $\to$ [[O(1) - Constant Time\|$O(1)$]].
- **Hình dung:** Giống như chồng đĩa ăn tiệc. Bạn chỉ có thể đặt đĩa mới lên trên cùng, và khi lấy đĩa ra rửa bạn cũng phải nhấc chiếc đĩa trên cùng ra trước. Muốn lấy đĩa ở đáy, bạn phải dọn hết đĩa ở trên.

---

## 2. Ứng Dụng Thực Tế & Thiết Kế Hệ Thống
- **Call Stack của Hệ Điều Hành & Runtime:** Theo dõi các lời gọi hàm đệ quy trong [[Space Complexity]] và [[Recursion & Memoization]].
- **Tính năng Undo / Redo:** Trình soạn thảo Word, Photoshop (mỗi thao tác gõ được push vào stack, bấm Ctrl+Z là pop ra).
- **Trình duyệt Web:** Nút Back trên trình duyệt lưu lịch sử URL vào Stack.
- **Biên dịch & Phân tích cú pháp (Parsing):** Kiểm tra ngoặc hợp lệ `()[]{}` (Valid Parentheses), tính toán biểu thức tiền tố/hậu tố.

---

## 3. Các Pattern & Kỹ Thuật Nâng Cao
- **Monotonic Stack (Ngăn xếp đơn điệu):** Giữ các phần tử luôn tăng hoặc giảm dần để tìm "Phần tử lớn hơn gần nhất" (Next Greater Element) trong [[O(n) - Linear Time|$O(n)$]].
- Duyệt cây / đồ thị theo chiều sâu ([[Graph Representations & Traversal|DFS - Depth First Search]]).

---

## 🧠 Thẻ Ghi Nhớ Nhanh (Spaced Repetition)
Quy tắc hoạt động của Stack là gì và độ phức tạp của push/pop? #card
?
Quy tắc **LIFO (Last In, First Out)**. Độ phức tạp của cả `push`, `pop`, `peek` đều là **$O(1)$**.
Nêu 3 ứng dụng thực tế của Stack trong phần mềm? #card
?
1. Tính năng **Undo/Redo** (Ctrl+Z).
2. Nút **Back** của trình duyệt web.
3. **Call Stack** quản lý các tầng gọi hàm đệ quy của CPU/Runtime.
