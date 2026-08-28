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
  - Array
  - Dynamic Array
  - Mảng tĩnh
  - Mảng động
  - Mảng (Arrays)
---

# 📦 Mảng & Mảng Động (Array & Dynamic Array)

> [[00 - Master Dashboard|🧭 Dashboard]] / [[Master MOC|🗺️ Master MOC]] / [[Roadmap|📋 Roadmap]]

---

## 1. Bản Chất Cốt Lõi (Mental Model)
- **Mảng tĩnh (Static Array):** Là một khối các ô nhớ **liên tiếp nhau** (contiguous memory block) trong RAM với kích thước cố định được cấp phát từ trước.
- **Mảng động (Dynamic Array / ArrayList / Vector):** Là một lớp bọc thông minh quanh Mảng tĩnh. Khi mảng đầy, nó tự động cấp phát một vùng nhớ mới to gấp đôi ($2\times$) và sao chép toàn bộ phần tử cũ sang.
- **Hình dung:** Giống như dãy tủ đựng đồ được đánh số thứ tự từ $0, 1, 2\dots$ cạnh nhau. Muốn lấy đồ ở tủ số 5, bạn bước thẳng tới tủ số 5 trong $O(1)$. Nhưng nếu muốn nhét thêm một tủ vào giữa, bạn phải dịch chuyển toàn bộ các tủ phía sau sang một ô.

---

## 2. Bảng Độ Phức Tạp (Complexity Sheet)

| Thao Tác | Static Array | Dynamic Array (Amortized) | Ghi Chú Bản Chất |
| :--- | :--- | :--- | :--- |
| **Truy cập (Read by Index)** | [[O(1) - Constant Time\|$O(1)$]] | [[O(1) - Constant Time\|$O(1)$]] | Tính toán địa chỉ bộ nhớ trực tiếp |
| **Tìm kiếm giá trị (Search)** | [[O(n) - Linear Time\|$O(n)$]] | [[O(n) - Linear Time\|$O(n)$]] | Duyệt tuần tự nếu chưa sắp xếp |
| **Chèn/Xóa ở cuối (Append/Pop)** | $O(1)$ (nếu còn chỗ) | [[O(1) - Constant Time\|$O(1)$]] | Amortized $O(1)$ khi resize $2\times$ |
| **Chèn/Xóa ở đầu/giữa** | [[O(n) - Linear Time\|$O(n)$]] | [[O(n) - Linear Time\|$O(n)$]] | Phải dịch chuyển các phần tử sau |

---

## 3. Sự Đánh Đổi (Trade-offs) & Đối Trọng

- 🟢 **Điểm mạnh (Superpower):**
  - Đọc dữ liệu nhanh nhất thế giới nhờ Cache Locality (CPU nạp trước các ô nhớ lân cận vào L1/L2 cache).
  - Tiết kiệm bộ nhớ hơn Linked List vì không tốn dung lượng lưu trữ con trỏ `next`.
- 🔴 **Điểm yếu (Weakness):**
  - Chèn và xóa cực kỳ đắt đỏ ($O(n)$).
  - Cần một vùng nhớ liên tục lớn; khi mảng động resize $2\times$ sẽ có một thao tác bị lag tạm thời ($O(n)$ spike).
- ⚖️ **So sánh với [[Linked List]]:** Dùng Array khi đọc nhiều, sửa ít (Read-heavy). Dùng Linked List khi chèn/xóa liên tục ở đầu/cuối (Write/Insert-heavy).

---

## 4. Các Pattern & Bài Toán Thực Chiến
- [[Two Pointers Pattern]]: Tìm cặp phần tử, đảo ngược mảng, loại bỏ trùng lặp.
- [[Sliding Window Pattern]]: Tìm chuỗi con / mảng con liên tiếp tối ưu.
- [[Binary Search]]: Tìm kiếm siêu tốc $O(\log n)$ khi mảng đã sắp xếp.

---

## 🧠 Thẻ Ghi Nhớ Nhanh (Spaced Repetition)
Tại sao truy cập mảng theo index lại đạt $O(1)$? #card
?
Vì các phần tử nằm trong các ô nhớ liên tiếp nhau, địa chỉ ô nhớ được tính tức thì bằng: $\text{Địa chỉ} = \text{Gốc} + \text{index} \times \text{size}$.
Khái niệm "Amortized $O(1)$" khi thêm phần tử vào cuối Dynamic Array có nghĩa là gì? #card
?
Phần lớn các lần thêm vào cuối chỉ mất $O(1)$. Chỉ hiếm hoi khi mảng đầy mới mất $O(n)$ để nhân đôi dung lượng và copy phần tử. Trung bình cộng chi phí trên hàng nghìn lần thêm vẫn xấp xỉ $O(1)$.
