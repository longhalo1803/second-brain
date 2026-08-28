---
tags:
  - dsa
  - mental-model
  - algorithmic-thinking
stage: 1
type: mental-model
status: completed
created: 2026-08-24
updated: 2026-08-27
aliases:
  - Algorithmic Thinking
  - Tư duy thuật toán
---

# 🧠 Tư Duy Thuật Toán (Algorithmic Thinking)

> [[00 - Master Dashboard|🧭 Dashboard]] / [[Master MOC|🗺️ Master MOC]] / [[Big-O Notation - MOC|⚡ Big-O MOC]]

---

## 1. Bản Chất Cốt Lõi (Mental Model)

- **Không phải là học thuộc code:** Tư duy thuật toán không phải là việc bạn nhớ từng cú pháp của hàng trăm thuật toán.
- **Kỹ năng bẻ gãy vấn đề (Deconstruction):** Là năng lực chuyển hóa một bài toán mơ hồ ngoài đời thực thành một tập hợp hữu hạn các bước chỉ dẫn rõ ràng, logic mà máy tính có thể thực thi chính xác.
- **Hình dung sinh động:** Hãy tưởng tượng thuật toán giống như **công thức làm bánh tiêu chuẩn** hay **bản đồ định vị GPS**:
  - Dù ai là người nấu bánh, nếu tuân theo đúng thứ tự và tỷ lệ nguyên liệu, chiếc bánh luôn ra lò hoàn hảo.
  - Khi gặp ngã rẽ hoặc tắc đường, thuật toán định tuyến sẽ tự động tính toán lại lộ trình tối ưu nhất dựa trên các quy tắc xác định.

---

## 2. 5 Nguyên Tắc Vàng Của Một Thuật Toán Chuẩn

Để bẻ nhỏ bài toán thành các bước máy tính hiểu được, giải pháp của bạn phải thỏa mãn 5 tiêu chí:

1. **Định nghĩa rõ Input & Output cùng Điều Kiện Tiên Quyết (Preconditions):**
   - *Ví dụ:* Muốn tìm một số trong danh sách: Input là dãy số và số cần tìm, Output là vị trí index (hoặc thông báo `-1`).
   - *Điều kiện tiên quyết:* Để áp dụng [[Binary Search|Tìm kiếm nhị phân $O(\log n)$]], Input **bắt buộc phải được sắp xếp trước**.
2. **Thứ tự thực hiện xác định (Specific Order):** Máy tính là thực thể tuân lệnh mù quáng. Đảo lộn thứ tự các bước sẽ dẫn đến sụp đổ toàn bộ logic.
3. **Mỗi bước phải tường minh và đơn lẻ (Explicit & Atomic):** Không dùng các lệnh mơ hồ kiểu *"tìm đến khi thấy"*. Mỗi lệnh phải là một thao tác cơ bản (so sánh, gán, tăng biến đếm).
4. **Luôn trả về kết quả (Produce a result):** Chương trình phải trả về một kết quả rõ ràng (dù là `null`, `-1` hay `false`) để hệ thống biết đã xử lý xong.
5. **Tính hữu hạn (Finiteness):** Thuật toán bắt buộc phải kết thúc sau một số bước hữu hạn, không được rơi vào vòng lặp vô tận (infinite loop).

---

## 3. Tư Duy Của Kiến Trúc Sư (Architect's Mindset)

- **Không có giải pháp "Tốt nhất", chỉ có giải pháp "Phù hợp nhất":** Một giải pháp xuất sắc phụ thuộc hoàn toàn vào bối cảnh:
  - Dữ liệu tĩnh hay cập nhật liên tục (Read-heavy vs Write-heavy)?
  - Bộ nhớ RAM có bị thắt chặt không (Embedded systems vs Cloud servers)?
- **Luôn bắt đầu bằng Brute-Force rồi mới Tối ưu:** Đừng cố viết code tối ưu ngay giây đầu tiên. Hãy giải quyết bài toán bằng cách ngây ngô nhất (Brute Force), đo lường độ phức tạp [[Big-O Notation - MOC|Big O]], sau đó nhận diện nút thắt cổ chai và áp dụng cấu trúc dữ liệu hoặc Pattern thích hợp.
- **Ranh giới và Trường hợp biên (Edge Cases):** Luôn thử thách thuật toán với các trường hợp cực đoan: Mảng rỗng (`[]`), mảng có 1 phần tử, mảng chứa toàn phần tử trùng lặp, số âm, hoặc giá trị tràn số nguyên (`Integer Overflow`).

---

## 4. Nghiên Cứu Tình Huống: Trò Chơi Đoán Số (The Guessing Game)

*Bài toán: Đoán một số nguyên bí mật nằm trong khoảng từ $1$ đến $100$ với số lần hỏi ít nhất.*

### Cách 1: Đoán tuần tự (Brute-force)
- **Bản chất:** Áp dụng [[Linear Search|Tìm kiếm tuyến tính]]. Đoán lần lượt $1, 2, 3, \dots$
- **Hiệu năng:** Rơi vào độ phức tạp [[O(n) - Linear Time|$O(n)$]]. Trong trường hợp xấu nhất, bạn mất đúng 100 lần đoán.

### Cách 2: Chia để trị (Divide and Conquer)
- **Bản chất:** Áp dụng [[Binary Search|Tìm kiếm nhị phân]]. Hỏi số đó lớn hơn hay nhỏ hơn $50$? Cắt bỏ $50\%$ phạm vi không phù hợp. Lặp lại với điểm giữa mới ($25$ hoặc $75$).
- **Hiệu năng:** Độ phức tạp [[O(log n) - Logarithmic Time|$O(\log n)$]]. Với 100 số, bạn chỉ mất tối đa $\approx \lceil \log_2(100) \rceil = 7$ lần đoán. Với $1$ triệu số, bạn chỉ mất tối đa $20$ lần đoán!

---

## 🧠 Thẻ Ghi Nhớ & Câu Hỏi Tự Vấn (Active Recall)
Nêu 5 nguyên tắc vàng của một thuật toán máy tính? #card
?
1. Input/Output & Preconditions rõ ràng.
2. Thứ tự các bước xác định.
3. Mỗi bước tường minh (Atomic).
4. Luôn trả về kết quả hữu ích.
5. Thời gian chạy hữu hạn.
Khi tiếp cận một bài toán DSA mới, thứ tự tư duy đúng đắn là gì? #card
?
1. Làm rõ Input/Output và Edge Cases.
2. Đưa ra giải pháp Brute-force và tính Big-O.
3. Tìm nút thắt cổ chai (Bottleneck) để tối ưu bằng cấu trúc dữ liệu/Pattern.
4. Đánh giá Trade-off Time/Space.
5. Viết code sạch và test các trường hợp biên.
