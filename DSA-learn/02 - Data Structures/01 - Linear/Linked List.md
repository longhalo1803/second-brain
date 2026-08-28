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
  - Linked List
  - Singly Linked List
  - Doubly Linked List
  - Danh sách liên kết
  - Linked Lists
---

# 🔗 Danh Sách Liên Kết (Linked List)

> [[00 - Master Dashboard|🧭 Dashboard]] / [[Master MOC|🗺️ Master MOC]] / [[Roadmap|📋 Roadmap]]

---

## 1. Bản Chất Cốt Lõi (Mental Model)
- **Định nghĩa:** Là tập hợp các nút (Node) nằm rải rác bất kỳ đâu trong bộ nhớ RAM, được kết nối với nhau thông qua các **con trỏ tham chiếu (Pointers)**. Mỗi Node gồm 2 phần: `Value` (Dữ liệu) và `Next` (Địa chỉ node tiếp theo).
- **Phân loại:**
  - *Singly Linked List:* Con trỏ 1 chiều (`Node -> Next`).
  - *Doubly Linked List:* Con trỏ 2 chiều (`Node -> Prev` và `Node -> Next`).
- **Hình dung:** Giống như một đoàn tàu lửa nối toa bằng các móc xích, hoặc trò chơi săn kho báu: mỗi manh mối chỉ chứa dữ liệu và một tấm bản đồ chỉ đường tới vị trí của manh mối tiếp theo.

---

## 2. Bảng Độ Phức Tạp (Complexity Sheet)

| Thao Tác | Linked List | So Với [[Array & Dynamic Array\|Array]] | Ghi Chú |
| :--- | :--- | :--- | :--- |
| **Truy cập qua Index ($k$)** | [[O(n) - Linear Time\|$O(n)$]] | 🟢 Array ($O(1)$) | Phải duyệt tuần tự từ đầu (`head`) |
| **Tìm kiếm giá trị** | [[O(n) - Linear Time\|$O(n)$]] | 🟡 Bằng nhau | Duyệt từng node |
| **Chèn/Xóa ở đầu (`head`)** | [[O(1) - Constant Time\|$O(1)$]] | 🔴 Array ($O(n)$) | Chỉ cần đổi con trỏ `head` |
| **Chèn/Xóa tại con trỏ đã biết**| [[O(1) - Constant Time\|$O(1)$]] | 🔴 Array ($O(n)$) | Không cần dịch chuyển ô nhớ |

---

## 3. Sự Đánh Đổi (Trade-offs) & Đối Trọng

- 🟢 **Điểm mạnh (Superpower):**
  - Chèn và xóa cực nhanh trong $O(1)$ khi đã cầm con trỏ tại vị trí đó.
  - Cấp phát bộ nhớ linh hoạt, không yêu cầu vùng nhớ liên tục khổng lồ như Array.
- 🔴 **Điểm yếu (Weakness):**
  - Không hỗ trợ truy cập ngẫu nhiên (Random Access $O(1)$).
  - Tốn thêm bộ nhớ RAM phụ trợ để lưu trữ con trỏ `next` / `prev` cho từng node.
  - Kém thân thiện với CPU Cache (Cache Misses) do các node nằm rải rác trong RAM.
- ⚖️ **Ứng dụng hệ thống:** Doubly Linked List là thành phần cốt lõi tạo nên cấu trúc [[LRU Cache]] siêu tốc khi kết hợp với [[Hash Table & HashSet]].

---

## 🧠 Thẻ Ghi Nhớ Nhanh (Spaced Repetition)
Tại sao việc chèn/xóa ở đầu Linked List lại đạt $O(1)$ trong khi Array mất $O(n)$? #card
?
Vì Linked List chỉ cần gán lại con trỏ `new_node.next = head` và cập nhật `head = new_node` (1 phép gán), không cần dịch chuyển bất kỳ phần tử nào khác trong RAM.
Khi nào nên ưu tiên dùng Doubly Linked List hơn Singly Linked List? #card
?
Khi cần duyệt hoặc xóa node theo cả 2 chiều, hoặc khi xây dựng các cấu trúc như [[LRU Cache]] và [[Queue & Deque|Deque]] yêu cầu xóa một node đã biết trong $O(1)$ mà không cần duyệt lại từ đầu để tìm node phía trước.
