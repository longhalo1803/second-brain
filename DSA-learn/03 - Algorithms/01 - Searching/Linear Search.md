---
tags:
  - dsa
  - algorithm
  - searching
stage: 3
type: algorithm
status: completed
created: 2026-08-27
updated: 2026-08-27
aliases:
  - Linear Search
  - Tìm kiếm tuyến tính
  - Thuật toán tìm kiếm tuyến tính (Linear Search)
---

# 🔍 Tìm Kiếm Tuyến Tính (Linear Search)

> [[00 - Master Dashboard|🧭 Dashboard]] / [[Master MOC|🗺️ Master MOC]] / [[Roadmap|📋 Roadmap]]

---

## 1. Bản Chất Cốt Lõi (Mental Model)
- **Ý tưởng:** Duyệt tuần tự từ phần tử đầu tiên đến phần tử cuối cùng của danh sách cho đến khi tìm thấy phần tử mục tiêu.
- **Không yêu cầu điều kiện:** Hoạt động trên mọi tập dữ liệu (kể cả mảng chưa sắp xếp, [[Linked List]]).
- **Độ phức tạp:**
  - Best Case: [[O(1) - Constant Time\|$O(1)$]] (nằm ngay ở vị trí đầu tiên).
  - Worst Case / Average: [[O(n) - Linear Time\|$O(n)$]] (nằm ở cuối hoặc không tồn tại trong danh sách).
  - Space: [[O(1) - Constant Time\|$O(1)$]].

---

## 2. So Sánh: Linear Search vs [[Binary Search]]

| Tiêu Chí | Linear Search | Binary Search |
| :--- | :--- | :--- |
| **Yêu cầu dữ liệu** | Không cần sắp xếp | **Bắt buộc đã sắp xếp** |
| **Cấu trúc dữ liệu** | Mọi cấu trúc (Array, [[Linked List]]) | Chỉ hiệu quả trên Mảng (Array) có Random Access |
| **Độ phức tạp thời gian** | [[O(n) - Linear Time\|$O(n)$]] | [[O(log n) - Logarithmic Time\|$O(\log n)$]] |
| **Số bước với $N=10^6$** | Tối đa $1.000.000$ bước | Tối đa khoảng $20$ bước |

---

## 🧠 Thẻ Ghi Nhớ Nhanh (Spaced Repetition)
Khi nào Linear Search lại là lựa chọn duy nhất/tốt hơn Binary Search? #card
?
1. Khi tập dữ liệu **hoàn toàn chưa được sắp xếp** và chúng ta chỉ cần **tìm kiếm đúng 1 lần** (chi phí sắp xếp $O(n \log n)$ sẽ đắt hơn quét $O(n)$).
2. Khi cấu trúc dữ liệu là **Singly Linked List** (không hỗ trợ nhảy tới vị trí giữa `mid` trong $O(1)$).
