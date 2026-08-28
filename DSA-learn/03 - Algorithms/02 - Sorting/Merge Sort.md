---
tags:
  - dsa
  - algorithm
  - sorting
  - divide-and-conquer
stage: 5
type: algorithm
status: completed
created: 2026-08-27
updated: 2026-08-27
aliases:
  - Merge Sort
  - Sắp xếp trộn
---

# 🔀 Sắp Xếp Trộn (Merge Sort)

> [[00 - Master Dashboard|🧭 Dashboard]] / [[Master MOC|🗺️ Master MOC]] / [[Roadmap|📋 Roadmap]]

---

## 1. Bản Chất Cốt Lõi (Mental Model)
- **Tư tưởng Chia để trị (Divide and Conquer):**
  1. **Chia (Divide):** Chia đôi mảng thành 2 nửa bằng nhau cho đến khi mỗi mảng con chỉ còn 1 phần tử (đã tự sắp xếp).
  2. **Trị (Conquer / Merge):** Trộn (merge) 2 mảng con đã sắp xếp thành 1 mảng mới lớn hơn có thứ tự hoàn chỉnh.
- **Tính ổn định (Stable Sort):** Giữ nguyên thứ tự tương đối của các phần tử có giá trị bằng nhau.

---

## 2. Bảng Độ Phức Tạp (Complexity Analysis)

| Trường Hợp | Thời Gian (Time Complexity) | Không Gian Bộ Nhớ (Space Complexity) |
| :--- | :--- | :--- |
| **Tốt nhất (Best Case)** | [[O(n log n) - Linearithmic Time\|$O(n \log n)$]] | [[O(n) - Linear Time\|$O(n)$]] (mảng phụ để trộn) |
| **Trung bình (Average)** | [[O(n log n) - Linearithmic Time\|$O(n \log n)$]] | [[O(n) - Linear Time\|$O(n)$]] |
| **Xấu nhất (Worst Case)** | [[O(n log n) - Linearithmic Time\|$O(n \log n)$]] | [[O(n) - Linear Time\|$O(n)$]] |

---

## 3. Sự Đánh Đổi (Trade-offs)
- 🟢 **Điểm mạnh:** Luôn đảm bảo hiệu năng $O(n \log n)$ trong mọi hoàn cảnh, không bao giờ bị rơi vào trường hợp xấu như Quick Sort. Cực kỳ tối ưu khi sắp xếp [[Linked List]] và dữ liệu ngoại tuyến (External Sorting trên đĩa cứng).
- 🔴 **Điểm yếu:** Tốn thêm **$O(n)$ bộ nhớ RAM phụ trợ** để tạo mảng tạm trong quá trình trộn (Merge).

---

## 🧠 Thẻ Ghi Nhớ Nhanh (Spaced Repetition)
Tại sao Merge Sort luôn đảm bảo $O(n \log n)$ trong mọi trường hợp? #card
?
Vì cây đệ quy luôn được chia đôi hoàn hảo thành $\log_2(n)$ tầng, và ở mỗi tầng, thao tác trộn hai mảng con luôn duyệt qua chính xác $n$ phần tử ($n \times \log n$).
Nhược điểm lớn nhất của Merge Sort so với Quick Sort là gì? #card
?
**Tốn $O(n)$ bộ nhớ phụ (Auxiliary Space)** cho mảng tạm, trong khi Quick Sort có thể chạy tại chỗ (In-place).
