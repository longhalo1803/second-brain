---
tags:
  - dsa
  - big-o
  - logarithmic-time
stage: 1
type: big-o
status: completed
created: 2026-08-24
updated: 2026-08-27
aliases:
  - O(log n)
  - Logarithmic Time
  - Thời gian logarit
---

# 🟢 O(log n) - Logarithmic Time (Thời Gian Logarit)

> [[00 - Master Dashboard|🧭 Dashboard]] / [[Master MOC|🗺️ Master MOC]] / [[Big-O Notation - MOC|⚡ Big-O MOC]]

---

## 1. Bản Chất Cốt Lõi (Mental Model)
Khi kích thước dữ liệu đầu vào $n$ tăng **gấp đôi**, số bước tính toán chỉ tăng thêm **đúng 1 bước duy nhất**. Ở mỗi bước thực thi, bạn **loại bỏ được một nửa ($50\%$)** khối lượng dữ liệu không liên quan.

> [!TIP]
> **Hình dung sinh động:** Tìm một từ trong cuốn từ điển 1.000 trang. Bạn lật đôi trang sách ở trang 500, thấy từ cần tìm nằm ở nửa sau $\to$ vứt bỏ hoàn toàn 500 trang đầu tiên vào sọt rác. Lặp lại quá trình xé đôi này, bạn tìm ra kết quả chỉ sau khoảng 10 lần lật sách thay vì lật từng trang một!

---

## 2. Dấu Hiệu Nhận Biết (Code Triggers)
- Không gian tìm kiếm liên tục bị **chia đôi** (hoặc chia 3, chia $k$) sau mỗi vòng lặp.
- Vòng lặp có bước nhảy nhân hoặc chia biến đếm (ví dụ: `i = i * 2` hoặc `i = i / 2`).
- Cấu trúc dữ liệu dạng cây phân nhánh cân bằng.

---

## 3. Cấu Trúc Dữ Liệu & Thuật Toán Liên Quan
- [[Binary Search|Thuật toán Tìm kiếm nhị phân (Binary Search)]] trên mảng đã sắp xếp.
- [[Binary Search Tree (BST)|Cây tìm kiếm nhị phân cân bằng (AVL Tree, Red-Black Tree)]]: Tìm kiếm, chèn, xóa.
- [[Binary Heap & Priority Queue|Cây vun đống (Heap)]]: Thao tác thêm/xóa phần tử duy trì tính chất Heap (`heapify-up`, `heapify-down`).

---

## 4. Cách Tối Ưu Thực Tế (Architect's View)
- **Vũ khí tối thượng cho dữ liệu lớn:** $O(\log n)$ có tốc độ tiệm cận với $O(1)$. Với $1$ triệu bản ghi, $\log_2(10^6) \approx 20$ bước. Với $1$ tỷ bản ghi, $\log_2(10^9) \approx 30$ bước!
- **Chiến lược tối ưu:** Nếu hệ thống của bạn phải tìm kiếm nhiều lần trên một mảng chưa sắp xếp ($O(n)$ mỗi lần tìm), hãy đầu tư chi phí một lần để **sắp xếp mảng** bằng [[Merge Sort]] hoặc [[Quick Sort]] ($O(n \log n)$), sau đó biến toàn bộ các truy vấn tìm kiếm về sau thành $O(\log n)$ bằng [[Binary Search]].

---

## 🧠 Thẻ Ghi Nhớ Nhanh (Spaced Repetition)
Tại sao $O(\log n)$ lại mở rộng (scale) cực tốt khi dữ liệu phình to? #card
?
Vì hàm logarit tăng trưởng cực kỳ chậm. Khi dữ liệu tăng từ $1.000 \to 1.000.000$ (tăng 1000 lần), số bước tính toán $\log_2(n)$ chỉ tăng từ $10 \to 20$ bước (tăng đúng 10 bước).
Thuật toán nào điển hình nhất cho độ phức tạp $O(\log n)$ và điều kiện tiên quyết của nó là gì? #card
?
[[Binary Search|Binary Search (Tìm kiếm nhị phân)]]. Điều kiện tiên quyết bắt buộc là tập dữ liệu đầu vào phải **được sắp xếp trước**.
