---
tags:
  - dsa
  - big-o
  - linearithmic-time
stage: 1
type: big-o
status: completed
created: 2026-08-24
updated: 2026-08-27
aliases:
  - O(n log n)
  - Linearithmic Time
  - Quasilinear Time
  - Thời gian tựa tuyến tính
---

# 🟠 O(n log n) - Linearithmic Time (Thời Gian Tựa Tuyến Tính)

> [[00 - Master Dashboard|🧭 Dashboard]] / [[Master MOC|🗺️ Master MOC]] / [[Big-O Notation - MOC|⚡ Big-O MOC]]

---

## 1. Bản Chất Cốt Lõi (Mental Model)
Là sự kết hợp nhân chéo giữa **Tuyến tính $O(n)$** và **Logarit $O(\log n)$**. 
Nghĩa là bài toán thực hiện một chiến lược chia đôi vấn đề thành $\log n$ tầng phân cấp (giống như dựng cây), và ở **mỗi tầng phân cấp đó**, thuật toán phải duyệt qua toàn bộ $n$ phần tử để tổng hợp hoặc so sánh.

> [!TIP]
> **Hình dung sinh động:** Bạn là trọng tài tổ chức giải đấu bóng đá loại trực tiếp cho 64 đội. Để tìm ra nhà vô địch, giải đấu cần trải qua $\log_2(64) = 6$ vòng đấu. Ở mỗi vòng đấu, tất cả các cầu thủ còn lại đều phải ra sân thi đấu ($O(n)$ nỗ lực cho mỗi tầng).

---

## 2. Dấu Hiệu Nhận Biết (Code Triggers)
- Xuất hiện ở các thuật toán theo tư tưởng **Chia để trị (Divide and Conquer)**.
- Một hàm đệ quy chia đôi mảng dữ liệu (chiều sâu cây đệ quy là $\log n$), kết hợp với một vòng lặp tuyến tính $O(n)$ tại mỗi tầng để gộp (merge) hoặc phân vùng (partition) dữ liệu lại.

---

## 3. Cấu Trúc Dữ Liệu & Thuật Toán Liên Quan
- Thuật toán sắp xếp so sánh tối ưu:
  - [[Merge Sort|Sắp xếp Trộn (Merge Sort)]] — Luôn luôn đảm bảo $O(n \log n)$ trong mọi trường hợp.
  - [[Quick Sort|Sắp xếp Nhanh (Quick Sort)]] — Trung bình $O(n \log n)$ với tốc độ thực thi tại chỗ (in-place) cực nhanh.
  - [[Binary Heap & Priority Queue#Heap Sort|Sắp xếp Vun đống (Heap Sort)]] — $O(n \log n)$ ổn định và không tốn bộ nhớ phụ.

---

## 4. Cách Tối Ưu Thực Tế (Architect's View)
- **Tiêu chuẩn vàng toán học của Sắp Xếp (Comparison Sort Bound):** Về mặt lý thuyết thông tin, không một thuật toán sắp xếp dựa trên phép so sánh hai phần tử nào có thể chạy nhanh hơn $O(n \log n)$ trong trường hợp tổng quát.
- **Quy tắc đầu tư chi phí một lần:** Trong thiết kế cơ sở dữ liệu, ta sẵn sàng trả chi phí $O(n \log n)$ một lần duy nhất lúc khởi tạo dữ liệu để tạo chỉ mục (Index) hoặc sắp xếp bảng, sau đó hưởng lợi ích từ các truy vấn tìm kiếm siêu tốc $O(\log n)$ hoặc $O(1)$ hàng triệu lần về sau.

---

## 🧠 Thẻ Ghi Nhớ Nhanh (Spaced Repetition)
Tại sao $O(n \log n)$ được coi là giới hạn tối ưu của các thuật toán sắp xếp dựa trên so sánh? #card
?
Vì có $n!$ hoán vị có thể có của $n$ phần tử. Chiều cao tối thiểu của cây quyết định so sánh là $\log_2(n!) \approx n \log_2(n) - n \log_2(e) = \Omega(n \log n)$.
Phân biệt độ phức tạp thời gian của Merge Sort và Quick Sort? #card
?
- [[Merge Sort]]: Luôn luôn là $O(n \log n)$ ở cả Best, Average và Worst case (nhưng tốn $O(n)$ Space).
- [[Quick Sort]]: Trung bình là $O(n \log n)$, nhưng Worst case có thể rơi vào $O(n^2)$ nếu chọn Pivot xấu (nhưng chạy In-place $O(\log n)$ Space).
