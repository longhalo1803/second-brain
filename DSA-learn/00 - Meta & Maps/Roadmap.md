---
tags:
  - meta
  - dsa
  - roadmap
type: roadmap
status: in-progress
created: 2026-06-23
updated: 2026-08-27
aliases:
  - Lộ trình DSA
  - DSA Roadmap
---

# 📋 Lộ Trình Học DSA Cho Kỹ Sư & Kiến Trúc Sư Hệ Thống

> [[00 - Master Dashboard|🧭 Dashboard]] | [[Master MOC|🗺️ Master MOC]]

---

## 🎯 Triết Lý Cốt Lõi

Lộ trình này không yêu cầu bạn học thuộc lòng code của từng thuật toán hay cấu trúc dữ liệu. Nhiệm vụ của bạn là mở Obsidian lên, nối các liên kết (`links`) lại với nhau để hiểu rõ: **Khi có một bài toán, dữ liệu cần tổ chức theo hình thù nào, và nếu dùng nó, chúng ta phải đánh đổi điều gì?**

---

## 🚀 Giai Đoạn 1: Nền Tảng Tư Duy & Thước Đo Hệ Thống (Mental Models & Big O)

_Trước khi học bất kỳ cấu trúc nào, bạn phải biết cách đo lường độ hiệu quả của chúng._

- 🧠 **Tư duy thuật toán:** [[Algorithmic Thinking|Tư duy thuật toán (Algorithmic Thinking)]] — Kỹ năng chia nhỏ bài toán phức tạp thành các bước rõ ràng với input/output cụ thể.
- ⚡ **Ký hiệu Big O (Độ phức tạp Thời gian & Không gian):** [[Big-O Notation - MOC|Big-O Notation MOC]]
  - Hiểu rõ cách thuật toán phình to thế nào khi dữ liệu lớn lên: [[O(1) - Constant Time|$O(1)$]], [[O(log n) - Logarithmic Time|$O(\log n)$]], [[O(n) - Linear Time|$O(n)$]], [[O(n log n) - Linearithmic Time|$O(n \log n)$]] đến các mức nguy hiểm như [[O(n^2) - Quadratic Time|$O(n^2)$]], [[O(2^n) - Exponential Time|$O(2^n)$]], [[O(n!) - Factorial Time|$O(n!)$]].
  - Phân biệt [[Time Complexity|Độ phức tạp Thời gian]] vs [[Space Complexity|Độ phức tạp Không gian]].
- 📝 **Phương pháp ghi chú trên Obsidian:** Luôn bắt đầu giải bài toán bằng cách ngây ngô nhất (Brute Force), tính toán Big O của nó (thường là $O(n^2)$ hoặc tệ hơn), sau đó mới tìm cách tối ưu bằng cách đánh đổi RAM lấy Tốc độ.

---

## 📦 Giai Đoạn 2: Nhóm Cấu Trúc Dữ Liệu Tuyến Tính Cơ Bản (Trade-offs)

_Đây là nền tảng của lưu trữ dữ liệu. Hãy tạo các thẻ và liên kết sự đối nghịch của chúng với nhau._

- 📑 [[Array & Dynamic Array|Mảng (Arrays / Dynamic Arrays)]]: Đọc dữ liệu tức thì $O(1)$ vì các ô nhớ xếp cạnh nhau (contiguous memory), nhưng chèn/xóa chậm $O(n)$ do phải dịch chuyển toàn bộ phần tử.
- 🔗 [[Linked List|Danh sách liên kết (Singly / Doubly Linked Lists)]]: Chèn/xóa ngay lập tức $O(1)$ chỉ bằng cách thay đổi con trỏ, nhưng tốc độ tìm kiếm lại chậm $O(n)$ vì phải duyệt tuần tự.
- 🥞 [[Stack|Ngăn xếp (Stacks - LIFO)]]: Thao tác ở đỉnh (Top). _Áp dụng thực tế:_ Tính năng Undo/Redo, nút Back trên trình duyệt, theo dõi lệnh gọi hàm (Call Stack).
- 🚶 [[Queue & Deque|Hàng đợi (Queues - FIFO) & Hàng đợi hai đầu (Deque)]]: Phục vụ theo thứ tự vào trước - ra trước. _Áp dụng thực tế:_ Quản lý hàng chờ máy in, web server request queue, lịch sử trình duyệt điều hướng 2 chiều.
- ⚖️ **So sánh trực diện:** Khi nào dùng Array (thiên về đọc nhanh)? Khi nào dùng Linked List (thiên về chèn/xóa liên tục)?

---

## ⚙️ Giai Đoạn 3: Thuật Toán Cốt Lõi & Kỹ Thuật Lập Trình Cơ Bản

- 🔍 **Thuật toán Tìm kiếm (Searching):**
  - [[Linear Search|Tìm kiếm tuyến tính (Linear Search)]]: Chậm $O(n)$, duyệt từng phần tử.
  - [[Binary Search|Tìm kiếm nhị phân (Binary Search)]]: Cực nhanh $O(\log n)$, loại bỏ một nửa dữ liệu mỗi bước. _(Điều kiện bắt buộc: Dữ liệu phải được sắp xếp trước)_.
- 🔁 **Kỹ thuật Đệ quy & Ghi nhớ:** [[Recursion & Memoization|Đệ quy (Recursion) & Ghi nhớ (Memoization)]] — Cấu trúc bắt buộc gồm Base case (điều kiện dừng) và Recursive case. Phân tích chi phí Call Stack trong [[Space Complexity]].
- 🧩 **Quy hoạch động toàn diện (Dynamic Programming):** [[Dynamic Programming|Quy hoạch động (Dynamic Programming - DP)]] — Triết lý không tính lại những gì đã biết, Top-Down (Memoization) vs Bottom-Up (Tabulation), tối ưu không gian về $O(1)$, bài toán lưới 2D Unique Paths, trùm cuối 0/1 Knapsack và khung 3 bước giải quyết mọi bài toán DP.
- 🪙 **Thuật toán Tham lam (Greedy Algorithm):** [[Greedy Algorithm|Thuật toán Tham lam (Greedy Algorithm)]] — Quyết định tối ưu cục bộ tức thời, 2 điều kiện sống còn (Greedy Choice Property & Optimal Substructure), ứng dụng xếp lịch phòng họp, Fractional Knapsack vs 0/1 Knapsack, và so sánh đối đầu cùng Dynamic Programming.
- 📊 **Thuật toán sắp xếp cơ sở ($O(n^2)$):** `[[Bubble Sort]]`, `[[Selection Sort]]`, `[[Insertion Sort]]`. Biết để hiểu lý do tại sao chúng quá chậm khi dữ liệu chạm mốc hàng triệu bản ghi và không được dùng trong hệ thống thực tế.

---

## 🌳 Giai Đoạn 4: Kiến Trúc Tối Ưu Tìm Kiếm & Phân Cấp

_Cách các Cơ sở dữ liệu (Database) và công cụ tìm kiếm hoạt động._

- ⚡ [[Hash Table & HashSet|Bảng băm (Hashmaps) & Tập hợp băm (Hashsets)]]: "Vua" tìm kiếm. Biến khóa (key) thành vị trí bộ nhớ, lấy dữ liệu tức thì $O(1)$. Hashsets dùng để kiểm tra sự tồn tại không cần value. _Đánh đổi: Tốn bộ nhớ và rủi ro đụng độ (hash collision)_.
- 🌲 [[Binary Search Tree (BST)|Cây (Trees) & Cây tìm kiếm nhị phân (BST)]]: Tổ chức dữ liệu phân cấp (File Explorer, DOM Tree). BST đưa dữ liệu nhỏ sang trái, lớn sang phải giúp tìm kiếm $O(\log n)$. _Edge case:_ Nếu nhập dữ liệu đã sắp xếp sẵn vào BST, nó mọc lệch thành Linked List ($O(n)$) $\to$ Cần cây tự cân bằng (AVL, Red-Black Tree).
- 🔤 [[Trie (Prefix Tree)|Cây tiền tố (Trie)]]: Tối ưu hơn Hashmap trong việc tìm kiếm tiền tố. _Ứng dụng:_ Tự động điền (Autocomplete), gợi ý từ điển, router URL.

---

## 🎯 Giai Đoạn 5: Các "Mẫu" Thuật Toán Thực Chiến (Algorithmic Patterns)

_Thay vì cắm đầu giải hàng trăm bài ngẫu nhiên, hãy học cách nhận diện các "Mẫu" (Patterns) có thể tái sử dụng để tối ưu từ $O(n^2)$ xuống $O(n)$._

- 👥 [[Two Pointers Pattern|Hai con trỏ (Two Pointers)]]: Đặt con trỏ ở đầu và cuối di chuyển ngược chiều nhau, hoặc cùng chiều (Fast/Slow Pointers). Tuyệt vời để giải bài toán trên Mảng/Linked List đã sắp xếp.
- 🪟 [[Sliding Window Pattern|Cửa sổ trượt (Sliding Window)]]: Tạo một dải phần tử trượt từ trái sang phải để giải quyết các bài toán tìm chuỗi con (substring) hoặc mảng con liên tiếp lớn nhất/nhỏ nhất.
- ⚔️ **Sắp xếp nâng cao (Chia để trị - Divide and Conquer):**
  - [[Merge Sort|Sắp xếp Trộn (Merge Sort)]]: Luôn ổn định $O(n \log n)$, tốn không gian mảng phụ $O(n)$.
  - [[Quick Sort|Sắp xếp Nhanh (Quick Sort)]]: Chạy tại chỗ (In-place), cực nhanh trong thực tế ($O(n \log n)$ trung bình).

---

## 🏛️ Giai Đoạn 6: Cấu Trúc Hệ Thống Chuyên Sâu (Tầm Nhìn Kiến Trúc Sư)

_Học các cấu trúc dữ liệu kết hợp và chuyên biệt giải quyết bài toán quy mô lớn._

- 🏔️ [[Binary Heap & Priority Queue|Cấu trúc Heap (Min/Max Heap)]]: Luôn đẩy phần tử ưu tiên nhất lên đỉnh trong $O(1)$, cập nhật $O(\log n)$. _Ứng dụng:_ Task scheduler CPU, Top-K elements, giải thuật Dijkstra.
- 🕸️ [[Graph Representations & Traversal|Đồ thị (Graphs)]]: Giải quyết dữ liệu mạng lưới chằng chịt (Social Network, Google Maps). Học cách duyệt theo chiều sâu (DFS - dùng Stack) và duyệt theo chiều rộng (BFS - dùng Queue).
- 🔗 `[[Disjoint Set Union (DSU)]]`: Tìm mối liên kết trong hàng triệu nhóm dữ liệu với kỹ thuật Path Compression.
- 🌸 [[Bloom Filter|Bộ lọc Bloom (Bloom Filter)]]: Cấu trúc xác suất tốn cực ít RAM. Trả lời CHẮC CHẮN KHÔNG (100%) hoặc CÓ THỂ CÓ (sai số nhỏ). _Ứng dụng:_ Web cache, phòng ngừa cache penetration, chặn URL độc hại.
- 🔄 [[LRU Cache|Bộ nhớ đệm LRU (LRU Cache)]]: Kết hợp Hash Table ($O(1)$) + Doubly Linked List (giữ thứ tự). Quyết định loại bỏ dữ liệu ít dùng nhất khi bộ nhớ đầy.

---

## 📊 Tổng Kết & Định Hướng

Khi nắm vững 6 giai đoạn trên, việc tiếp cận bài toán trên LeetCode hay thiết kế hệ thống lớn sẽ trở thành phản xạ có cấu trúc:

1. Nhận diện dạng bài $\to$ 2. Chọn cấu trúc dữ liệu phù hợp $\to$ 3. Áp dụng Pattern tối ưu $\to$ 4. Đánh giá Trade-off Big O $\to$ 5. Triển khai code & kiểm thử Edge Cases.
