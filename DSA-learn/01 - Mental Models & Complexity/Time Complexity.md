---
tags:
  - dsa
  - big-o
  - time-complexity
stage: 1
type: mental-model
status: completed
created: 2026-08-24
updated: 2026-08-27
aliases:
  - Time Complexity
  - Độ phức tạp thời gian
---

# ⏳ Độ Phức Tạp Thời Gian (Time Complexity)

> [[00 - Master Dashboard|🧭 Dashboard]] / [[Master MOC|🗺️ Master MOC]] / [[Big-O Notation - MOC|⚡ Big-O MOC]]

---

## 1. Bản Chất Cốt Lõi (Mental Model)

- **Không đo bằng giây (Wall-clock Time):** Độ phức tạp thời gian (**Time Complexity**) không đo lường thời gian chạy của thuật toán bằng giây hay mili-giây, vì tốc độ này thay đổi phụ thuộc vào sức mạnh CPU, ngôn ngữ lập trình, hệ điều hành hay tải hệ thống.
- **Đo lường "Tốc độ tăng trưởng" (Growth Rate):** Bản chất thực sự của Time Complexity là đo lường **số lượng bước tính cơ bản (operations) sẽ phình to ra sao khi quy mô dữ liệu đầu vào ($n$) ngày càng lớn**.
- **Quy tắc tiệm cận (Asymptotic Analysis):** Luôn tập trung vào xu hướng khi $n \to \infty$ và bỏ qua các hằng số hoặc phép toán nhỏ.

---

## 2. Các Cấp Độ Time Complexity (Trực Quan Hóa Bằng Hình Tượng)

| Cấp Độ                                            | Hình Tượng Thực Tế                                                                                                                        | Hành Vi Khi $N$ Tăng         | Note Chi Tiết                      |
| :------------------------------------------------ | :---------------------------------------------------------------------------------------------------------------------------------------- | :--------------------------- | :--------------------------------- |
| [[O(1) - Constant Time\|$O(1)$]]                  | **Lấy hạt đậu đúng ô trên khay:** Bạn biết chính xác vị trí ô số 5, thò tay lấy ra ngay. 10 ô hay 1 triệu ô cũng chỉ mất đúng 1 thao tác. | Không đổi                    | [[O(1) - Constant Time]]           |
| [[O(log n) - Logarithmic Time\|$O(\log n)$]]      | **Tìm lá bài trong bộ bài ĐÃ SẮP XẾP:** Lật lá chính giữa, loại bỏ ngay $50\%$ số lá không phù hợp sau mỗi lần lật.                       | Tăng 1 bước khi $n$ nhân đôi | [[O(log n) - Logarithmic Time]]    |
| [[O(n) - Linear Time\|$O(n)$]]                    | **Tìm lá bài trong bộ bài LỘN XỘN:** Mò kim đáy bể, buộc phải lật tuần tự từ lá đầu đến lá cuối.                                          | Tỷ lệ thuận $1:1$            | [[O(n) - Linear Time]]             |
| [[O(n log n) - Linearithmic Time\|$O(n \log n)$]] | **Chia đôi lớp học để sắp hàng:** Chia đôi danh sách theo logarit và duyệt qua toàn bộ phần tử để gộp lại. Tiêu chuẩn vàng của sắp xếp.   | Nhanh hơn bậc 2              | [[O(n log n) - Linearithmic Time]] |
| [[O(n^2) - Quadratic Time\|$O(n^2)$]]             | **Bắt tay chéo toàn bộ hội trường:** Mỗi người phải lần lượt bắt tay với tất cả những người còn lại trong phòng. Vòng lặp lồng nhau.      | Tăng theo bình phương        | [[O(n^2) - Quadratic Time]]        |
| [[O(2^n) - Exponential Time\|$O(2^n)$]]           | **Tung đồng xu $n$ lần:** Mỗi đồng xu thêm vào nhân đôi tổng số trường hợp có thể xảy ra.                                                 | Nhân đôi mỗi khi $n+1$       | [[O(2^n) - Exponential Time]]      |
| [[O(n!) - Factorial Time\|$O(n!)$]]               | **Hoán vị xếp chỗ ngồi:** Với $N$ người, vị trí đầu có $N$ cách, vị trí 2 có $N-1$...                                                     | Phình to theo giai thừa      | [[O(n!) - Factorial Time]]         |

---

## 3. Trade-off (Sự Đánh Đổi) giữa Time Complexity và [[Space Complexity]]

Là một kỹ sư và kiến trúc sư hệ thống, bạn không chỉ nhìn vào thời gian chạy mà phải đặt nó lên bàn cân với dung lượng bộ nhớ. **[[Space Complexity]]** là lượng không gian RAM phụ trợ mà thuật toán chiếm dụng thêm để xử lý.

> [!IMPORTANT]
> **Định luật bất thành văn của Hệ thống:** *Chúng ta thường xuyên đánh đổi bộ nhớ (RAM/Space) để mua lại tốc độ xử lý (Time).*

### Ví Dụ Minh Họa: Bài Toán "Phân Loại Hạt Đậu"
- **Tình huống:** Bạn có hộp Đen chứa lẫn đậu đen/trắng, và hộp Trắng chứa lẫn đậu đen/trắng. Cần chuyển toàn bộ đậu đen về hộp Đen, đậu trắng về hộp Trắng.
- **Cách 1: Tiết kiệm RAM, Tốn Thời Gian ($O(1)$ Space $\to$ Chậm):** Bạn chỉ có 2 bàn tay. Bạn nhặt 1 hạt đậu trắng từ hộp Đen, cầm trên tay rồi bới tìm hạt đậu đen ở hộp Trắng để đổi chỗ. Việc bới móc và đổi chỗ từng cặp cực kỳ tốn thời gian.
- **Cách 2: Đánh đổi RAM lấy Tốc Độ ($O(N)$ Space $\to$ Siêu Tốc):** Đặt thêm một **chiếc hộp thứ 3 (Bộ nhớ phụ - Extra Container)**. Bạn đổ toàn bộ đậu trắng từ hộp Đen sang hộp tạm này $\to$ Đổ toàn bộ đậu đen từ hộp Trắng sang hộp Đen $\to$ Đổ đậu trắng từ hộp tạm sang hộp Trắng. Xong trong chớp mắt!

### Ứng Dụng Trong Kỹ Thuật Lập Trình
- Khi đối mặt với thuật toán tra cứu chậm $O(n^2)$, ta dùng cấu trúc [[Hash Table & HashSet|Hash Table]] hoặc mảng đệm [[LRU Cache|Cache]] ($O(n)$ Space) để lưu sẵn kết quả. Thao tác kiểm tra tồn tại từ $O(n)$ trở thành $O(1)$.
- Tăng chi phí bộ nhớ từ $O(1) \to O(n)$, nhưng giảm thời gian từ $O(n^2) \to O(n)$. Đây là sự đánh đổi kinh điển và tối ưu trong phát triển phần mềm hiện đại.

---

## 🧠 Thẻ Ghi Nhớ Nhanh (Spaced Repetition)
Tại sao thuật toán $O(\log n)$ lại nhanh vượt trội khi dữ liệu lớn? #card
?
Vì sau mỗi bước, thuật toán loại bỏ được một nửa ($50\%$) khối lượng dữ liệu còn lại. Ví dụ với 1 tỷ phần tử ($\approx 2^{30}$), chỉ mất khoảng 30 bước tính.
Thế nào là sự đánh đổi Space-Time Trade-off? #card
?
Sử dụng thêm tài nguyên bộ nhớ phụ trợ (RAM/Storage) như Hashmap, Lookup Table hay Cache để lưu trước trạng thái tính toán, qua đó giảm số bước tính toán (thời gian chạy) của chương trình.
