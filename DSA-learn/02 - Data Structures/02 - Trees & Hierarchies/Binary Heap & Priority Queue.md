---
tags:
  - dsa
  - data-structure
  - heap
  - tree
stage: 6
type: data-structure
status: completed
created: 2026-08-27
updated: 2026-08-27
aliases:
  - Heap
  - Heaps
  - Min Heap
  - Max Heap
  - Priority Queue
  - Cây vun đống
  - Hàng đợi ưu tiên
  - Heap Sort
  - Sắp xếp vun đống
---

# 🏔️ Cây Vun Đống & Hàng Đợi Ưu Tiên (Heap & Priority Queue)

> [[00 - Master Dashboard|🧭 Dashboard]] / [[Master MOC|🗺️ Master MOC]] / [[Roadmap|📋 Roadmap]]

---

## 1. Bản Chất Cốt Lõi (Mental Model)
- **Định nghĩa:** Là một cây nhị phân gần hoàn chỉnh (Complete Binary Tree) thỏa mãn **Tính chất Heap (Heap Property)**:
  - *Max-Heap:* Nút cha luôn lớn hơn hoặc bằng các nút con $\to$ Phần tử **Lớn nhất** luôn nằm ở đỉnh (Root).
  - *Min-Heap:* Nút cha luôn nhỏ hơn hoặc bằng các nút con $\to$ Phần tử **Nhỏ nhất** luôn nằm ở đỉnh (Root).
- **Cài đặt cực kỳ thông minh trong RAM:** Heap thường **không dùng con trỏ**, mà được lưu gọn gàng bên trong một [[Array & Dynamic Array|Mảng 1 chiều]]:
  - Nút con trái của vị trí $i$: `2 * i + 1`
  - Nút con phải của vị trí $i$: `2 * i + 2`
  - Nút cha của vị trí $i$: `(i - 1) // 2`

---

## 2. Bảng Độ Phức Tạp (Complexity Sheet)

| Thao Tác | Độ Phức Tạp | Bản Chất |
| :--- | :--- | :--- |
| **Xem phần tử ưu tiên nhất (Peek Min/Max)** | [[O(1) - Constant Time\|$O(1)$]] | Luôn nằm ở đầu mảng `arr[0]` |
| **Trích xuất phần tử cực đại/cực tiểu (Extract Min/Max)** | [[O(log n) - Logarithmic Time\|$O(\log n)$]] | Lấy `arr[0]`, đổi chỗ với phần tử cuối và `heapify-down` |
| **Chèn phần tử mới (Insert / Push)** | [[O(log n) - Logarithmic Time\|$O(\log n)$]] | Thêm vào cuối mảng và `heapify-up` |
| **Xây dựng Heap từ mảng thô (Build Heap)** | [[O(n) - Linear Time\|$O(n)$]] | Sử dụng giải thuật Floyd's Build Heap |

---

## 3. Ứng Dụng Thực Tế & Thiết Kế Hệ Thống
- **Lập lịch tác vụ CPU (Operating System Process Scheduler):** Tác vụ nào có độ ưu tiên cao nhất sẽ được đưa lên đầu để CPU xử lý trước.
- **Phòng Cấp Cứu Bệnh Viện (Triage System):** Bệnh nhân nguy kịch nhất luôn được cấp cứu trước, không phụ thuộc vào việc ai đến trước (khác với FIFO Queue).
- **Thuật toán Dijkstra & Prim:** Tìm đường đi ngắn nhất trên [[Graph Representations & Traversal|Đồ thị]].
- **Bài toán Top K Elements:** Tìm $K$ phần tử lớn nhất trong một luồng dữ liệu khổng lồ (Streaming data) mà không cần sắp xếp toàn bộ.

---

## 🧠 Thẻ Ghi Nhớ Nhanh (Spaced Repetition)
Tại sao Binary Heap lại được cài đặt bằng Mảng (Array) thay vì Node con trỏ? #card
?
Vì Heap là cây nhị phân gần hoàn chỉnh, việc ánh xạ các nút sang mảng theo công thức chỉ số (`2i+1`, `2i+2`) giúp **tiết kiệm bộ nhớ con trỏ** và tận dụng tối đa **CPU Cache Locality**.
Để tìm K phần tử lớn nhất trong 1 tỷ số, ta nên dùng Min-Heap hay Max-Heap kích thước K? #card
?
Dùng một **Min-Heap kích thước K**. Khi duyệt qua từng số, nếu số lớn hơn đỉnh Min-Heap thì loại bỏ đỉnh và thêm số mới vào. Sau khi duyệt xong, Min-Heap chứa chính xác K phần tử lớn nhất.
