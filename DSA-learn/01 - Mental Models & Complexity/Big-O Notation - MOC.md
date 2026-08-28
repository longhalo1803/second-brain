---
tags:
  - dsa
  - big-o
  - mental-model
  - moc
stage: 1
type: moc
status: completed
created: 2026-08-24
updated: 2026-08-27
aliases:
  - Big-O Notation
  - Ký hiệu Big-O
  - Đánh giá hiệu suất thuật toán
---

# ⚡ Big-O Notation & Complexity Hub (MOC)

> [[00 - Master Dashboard|🧭 Dashboard]] / [[Master MOC|🗺️ Master MOC]] / **⚡ Big-O MOC**

---

## 1. Bản Chất Cốt Lõi (Mental Model)

- **Định nghĩa:** Ký hiệu **Big O** ($O$) là một thước đo lý thuyết mô tả tốc độ tăng trưởng độ phức tạp của một thuật toán dưới dạng một hàm số phụ thuộc vào kích thước dữ liệu đầu vào ($n$).
- **"How code slows as data grows":** Big O trả lời câu hỏi: *Khi khối lượng dữ liệu phình to lên gấp 10, 100 hay 1 triệu lần, thời gian chạy và dung lượng RAM phát sinh sẽ phình to theo tỷ lệ nào?*
- **Không đo bằng giây (wall-clock time):** Tốc độ tính bằng giây phụ thuộc vào xung nhịp CPU, ngôn ngữ biên dịch hay môi trường phần cứng. Big O tập trung vào **số lượng bước tính cơ bản (operations/steps)**.
- **Bỏ qua hằng số và số hạng bậc thấp:** Khi $n \to \infty$, $O(2n + 50) \approx O(n)$, $O(n^2 + 1000n) \approx O(n^2)$.
- **Tập trung vào Trường Hợp Xấu Nhất (Worst-Case Scenario):** Big O đóng vai trò là cận trên (upper bound), đảm bảo hệ thống không bao giờ vượt quá ngưỡng tài nguyên dự tính trong tình huống ngặt nghèo nhất.

---

## 2. Hai Thước Đo Chính Của Hệ Thống

Mọi giải thuật trong khoa học máy tính đều được đặt trên bàn cân qua 2 lăng kính:

- [[Time Complexity|⏳ Time Complexity (Độ phức tạp Thời gian)]]: Đo lường số bước tính toán tăng lên thế nào theo quy mô dữ liệu $n$.
- [[Space Complexity|💾 Space Complexity (Độ phức tạp Không gian)]]: Đo lường lượng bộ nhớ RAM phụ trợ (working/extra storage) cần cấp phát thêm để thuật toán hoàn thành công việc.

⚖️ **Quy tắc vàng của Kiến trúc sư:** *Thường xuyên đánh đổi Không gian (RAM) để chuộc lấy Thời gian (Tốc độ).* Xem chi tiết tại [[Time Complexity#3. Trade-off (Sự Đánh Đổi) giữa Time Complexity và Space Complexity|Phân tích Đánh Đổi Trade-off]].

---

## 3. Bảng Phân Loại Toàn Diện Các Cấp Độ Big-O

| Cấp Độ | Ký Hiệu | Tên Gọi Tiếng Anh | Tăng Trưởng Khi Dữ Liệu $n$ Tăng | Ví Dụ Điển Hình | Note Chi Tiết |
| :--- | :--- | :--- | :--- | :--- | :--- |
| 🟢 Tuyệt đối | $O(1)$ | Constant Time | Không đổi (1 thao tác) | Truy xuất mảng qua index, tra cứu Hash Table | [[O(1) - Constant Time]] |
| 🟢 Rất nhanh | $O(\log n)$ | Logarithmic Time | Tăng 1 bước khi $n$ gấp đôi | [[Binary Search\|Tìm kiếm nhị phân]], Cây BST cân bằng | [[O(log n) - Logarithmic Time]] |
| 🟡 Tuyến tính | $O(n)$ | Linear Time | Tỷ lệ thuận $1:1$ với $n$ | Duyệt qua danh sách, [[Linear Search\|Tìm kiếm tuyến tính]] | [[O(n) - Linear Time]] |
| 🟠 Tựa tuyến tính | $O(n \log n)$ | Linearithmic Time | Nhanh hơn bậc 2, chuẩn sắp xếp | [[Merge Sort]], [[Quick Sort]], [[Binary Heap & Priority Queue#Heap Sort\|Heap Sort]] | [[O(n log n) - Linearithmic Time]] |
| 🔴 Bậc hai | $O(n^2)$ | Quadratic Time | Tăng theo bình phương $n^2$ | 2 vòng lặp lồng nhau, `[[Bubble Sort]]`, `[[Selection Sort]]` | [[O(n^2) - Quadratic Time]] |
| ☠️ Lũy thừa | $O(2^n)$ | Exponential Time | Tăng gấp đôi mỗi khi $n$ tăng 1 | Đệ quy Fibonacci không nhớ, vét cạn mật khẩu | [[O(2^n) - Exponential Time]] |
| ☢️ Giai thừa | $O(n!)$ | Factorial Time | Phình to cực đại theo $n!$ | Bài toán Người giao hàng (TSP), hoán vị $N$ phần tử | [[O(n!) - Factorial Time]] |

---

## 4. Nguyên Tắc Của Kiến Trúc Sư Hệ Thống (Architect's Mindset)

1. **Nhận diện và triệt tiêu vòng lặp lồng nhau ($O(n^2) \to O(n)$):** Khi thấy hai vòng `for` lồng nhau để tìm kiếm hoặc so sánh cặp, hãy tự hỏi: *"Liệu ta có thể ném dữ liệu vào một [[Hash Table & HashSet|Hash Table]] để kiểm tra trong $O(1)$, hạ toàn bộ thuật toán xuống $O(n)$ không?"*.
2. **Quy tắc Nút thắt cổ chai (Bottleneck Rule):** Độ phức tạp tổng thể của một hàm luôn bị chi phối bởi bước chậm nhất. Nếu hàm có 10 bước $O(1)$ nhưng có 1 bước $O(n \log n)$, độ phức tạp của hàm là $O(n \log n)$.
3. **Ý thức về dữ liệu nhỏ (Small Inputs):** Đôi khi thuật toán $O(n^2)$ hoặc $O(n)$ có cài đặt đơn giản và hằng số nhỏ sẽ chạy nhanh hơn $O(n \log n)$ trên tập dữ liệu dưới 50 phần tử. Nhưng trên tập dữ liệu triệu bản ghi, bậc Big O sẽ quyết định sự sống còn của hệ thống.

---

## 🧠 Ôn Tập Nhanh (Active Recall & Spaced Repetition)
Tại sao Big O không đo lường thời gian chạy bằng giây? #card
?
Vì thời gian chạy bằng giây phụ thuộc vào phần cứng (CPU), hệ điều hành và ngôn ngữ lập trình. Big O đo lường **số lượng bước tính toán (growth rate)** độc lập với phần cứng.
Nêu quy tắc "Đánh đổi Không gian lấy Thời gian" và ví dụ kinh điển? #card
?
Sử dụng thêm cấu trúc dữ liệu phụ trợ như [[Hash Table & HashSet|Hash Table]] ($O(n)$ Space) để nhớ trước các giá trị đã duyệt, từ đó triệt tiêu vòng lặp lồng nhau để giảm thời gian từ $O(n^2) \to O(n)$ Time.
