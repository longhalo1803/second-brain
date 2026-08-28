---
tags:
  - dsa
  - big-o
  - space-complexity
stage: 1
type: mental-model
status: completed
created: 2026-08-24
updated: 2026-08-27
aliases:
  - Space Complexity
  - Độ phức tạp không gian
  - Auxiliary Space
---

# 💾 Độ Phức Tạp Không Gian (Space Complexity)

> [[00 - Master Dashboard|🧭 Dashboard]] / [[Master MOC|🗺️ Master MOC]] / [[Big-O Notation - MOC|⚡ Big-O MOC]]

---

## 1. Bản Chất Cốt Lõi (Mental Model)

- **Không phải kích thước dữ liệu gốc (Input Size):** Rất nhiều người nhầm lẫn rằng bộ nhớ chứa mảng đầu vào được tính vào Space Complexity. Thực chất, Space Complexity (hay chuẩn xác hơn là **Auxiliary Space / Working Storage**) đo lường **lượng RAM phụ trợ mà thuật toán tự động sinh thêm ra trong quá trình tính toán**.
- **Đo lường sự phình to theo $N$:** Đánh giá xem khi quy mô dữ liệu đầu vào ($n$) tăng gấp bội, thuật toán sẽ tiêu tốn thêm bao nhiêu ô nhớ trong trường hợp xấu nhất (Worst-case).
- **Nguy cơ tiềm ẩn:** Nếu không kiểm soát Space Complexity, hệ thống sẽ gặp các lỗi nghiêm trọng như `Out of Memory (OOM)` làm sập process, hoặc tràn ngăn xếp cuộc gọi `Stack Overflow` khi gọi đệ quy quá sâu.

---

## 2. Các Cấp Độ Space Complexity Thường Gặp

| Cấp Độ | Tên Gọi & Hành Vi | Ví Dụ Điển Hình |
| :--- | :--- | :--- |
| [[O(1) - Constant Time\|$O(1)$ Space]] | **Hoạt động tại chỗ (In-place):** Bộ nhớ phụ trợ cố định, chỉ dùng vài biến con trỏ hoặc biến tạm. | Tìm kiếm nhị phân dạng vòng lặp (Iterative [[Binary Search]]), kỹ thuật [[Two Pointers Pattern\|Hai con trỏ]]. |
| [[O(log n) - Logarithmic Time\|$O(\log n)$ Space]] | **Chi phí ẩn của Ngăn xếp gọi hàm (Call Stack):** Mỗi lần đệ quy chia đôi dữ liệu, hệ thống lưu một stack frame trong RAM. | Đệ quy [[Binary Search]], đệ quy [[Quick Sort]]. |
| [[O(n) - Linear Time\|$O(n)$ Space]] | **Cấp phát cấu trúc dữ liệu mới có kích thước tỷ lệ với $N$:** Tạo mảng phụ, bảng băm hoặc danh sách mới. | [[Merge Sort]] (cần mảng phụ để merge), khởi tạo [[Hash Table & HashSet\|Hash Table]] để lưu $n$ phần tử, BFS [[Queue & Deque\|Queue]]. |
| [[O(n^2) - Quadratic Time\|$O(n^2)$ Space]] | **Ma trận lưới $N \times N$:** Cấp phát bảng 2 chiều. | Biểu diễn [[Graph Representations & Traversal\|Đồ thị bằng Ma trận kề (Adjacency Matrix)]] kích thước $V \times V$. |

---

## 3. Bản Chất Trade-off: Đánh Đổi RAM Lấy Tốc Độ

Xem chi tiết ví dụ minh họa chiếc hộp thứ 3 tại [[Time Complexity#3. Trade-off (Sự Đánh Đổi) giữa Time Complexity và Space Complexity|Time vs Space Trade-off]].

Khi tối ưu hóa thuật toán:
- Muốn tốc độ nhanh: Cấp phát thêm bộ nhớ phụ như [[Hash Table & HashSet|Hash Table]], [[Recursion & Memoization|Bảng ghi nhớ Memoization]] để đưa thời gian từ $O(n^2) \to O(n)$.
- Khi bộ nhớ bị giới hạn nghiêm ngặt ($O(1)$ Space bắt buộc): Không được dùng Hash Table. Thay vào đó, ta sử dụng các kỹ thuật xử lý tại chỗ như sắp xếp In-place hoặc [[Two Pointers Pattern|Hai con trỏ]].

---

## 4. Lời Khuyên Của Kiến Trúc Sư Hệ Thống (Architect's Note)

1. **Cẩn trọng với Đệ Quy (Recursion Stack):** Code đệ quy thanh lịch và ngắn gọn, nhưng mỗi tầng đệ quy tốn một Stack Frame trong RAM. Nếu số tầng đệ quy lên tới hàng chục nghìn, chương trình sẽ crash ngay lập tức vì `Stack Overflow`. Luôn cân nhắc chuyển sang dạng vòng lặp (Iterative) khi làm việc với dữ liệu lớn.
2. **Cơ chế ngôn ngữ lập trình (Tail Call Optimization):** Một số ngôn ngữ như Swift hay C++ hỗ trợ tối ưu đệ quy đuôi (Tail Call Optimization), nhưng các ngôn ngữ như Python hay JavaScript mặc định không tối ưu Call Stack. Hãy thấu hiểu runtime của ngôn ngữ bạn đang dùng.

---

## 🧠 Thẻ Ghi Nhớ Nhanh (Spaced Repetition)
Phân biệt Space Complexity và Auxiliary Space? #card
?
**Space Complexity** = Bộ nhớ dữ liệu đầu vào (Input) + Bộ nhớ phụ trợ (Auxiliary Space). Khi đánh giá hiệu quả thuật toán, các kỹ sư thường tập trung vào **Auxiliary Space** (bộ nhớ phát sinh thêm do thuật toán yêu cầu).
Tại sao thuật toán đệ quy lại tiêu tốn bộ nhớ ngay cả khi không khai báo mảng mới? #card
?
Vì mỗi lần hàm đệ quy tự gọi chính nó, hệ điều hành phải cấp phát một **Stack Frame** trong Call Stack để lưu trữ địa chỉ trả về và các biến cục bộ, dẫn đến độ phức tạp không gian ít nhất là $O(\text{chiều sâu đệ quy})$.
