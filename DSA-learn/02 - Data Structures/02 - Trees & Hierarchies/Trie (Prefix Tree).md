---
tags:
  - dsa
  - data-structure
  - tree
  - trie
stage: 4
type: data-structure
status: completed
created: 2026-08-27
updated: 2026-08-27
aliases:
  - Trie
  - Prefix Tree
  - Cây tiền tố
---

# 🔤 Cây Tiền Tố (Trie / Prefix Tree)

> [[00 - Master Dashboard|🧭 Dashboard]] / [[Master MOC|🗺️ Master MOC]] / [[Roadmap|📋 Roadmap]]

---

## 1. Bản Chất Cốt Lõi (Mental Model)
- **Định nghĩa:** Là một cấu trúc cây cây nhiều nhánh chuyên biệt dùng để lưu trữ tập hợp các chuỗi ký tự (Strings). Mỗi cạnh hoặc nút đại diện cho một ký tự, và tất cả các từ có chung **tiền tố (prefix)** sẽ dùng chung nhánh cây đó.
- **Hình dung:** Giống như cây thư mục từ điển: gõ chữ `c` $\to$ rẽ vào nhánh `c`, gõ tiếp chữ `a` $\to$ rẽ tiếp vào nhánh `a`, gõ tiếp `t` $\to$ tìm thấy từ `cat`.

---

## 2. Bảng Độ Phức Tạp

Gọi $L$ là độ dài của từ khóa cần tìm kiếm/chèn, và $N$ là tổng số từ trong từ điển:

| Thao Tác                                               | Trie (Cây tiền tố)                 | So Với [[Hash Table & HashSet\|Hash Table]]    |     |                 |
| :----------------------------------------------------- | :--------------------------------- | :--------------------------------------------- | --- | --------------- |
| **Tìm kiếm từ chính xác (Exact Search)**               | $O(L)$                             | $O(L)$ (tính thời gian băm chuỗi)              |     |                 |
| **Tìm kiếm theo tiền tố (Prefix Search `startsWith`)** | 🟢 **$O(L)$**                      | 🔴 $O(N \times L)$ (phải quét toàn bộ từ điển) |     |                 |
| **Bộ nhớ (Space Complexity)**                          | Tốn $O(\text{Tổng số ký tự} \times | \Sigma                                         | )$  | $O(N \times L)$ |

---

## 3. Tại Sao Google Dùng Trie Thay Vì Hash Table Cho Gợi Ý Tìm Kiếm (Autocomplete)?

- **Vấn đề của Hash Table:** Để tìm xem có bao nhiêu từ bắt đầu bằng tiền tố `"algo"`, Hash Table không biết được vì `"algo"` và `"algorithm"` được băm ra 2 vị trí ô nhớ hoàn toàn ngẫu nhiên và xa nhau trong RAM. Hash Table buộc phải duyệt qua toàn bộ $N$ từ trong CSDL ($O(N)$).
- **Sức mạnh của Trie:** Chỉ cần đi bộ $4$ bước (`a -> l -> g -> o`), Trie lập tức đứng tại nút gốc của toàn bộ nhánh chứa mọi từ bắt đầu bằng `"algo"` trong thời gian chớp nhoáng $O(L)$!

---

## 🧠 Thẻ Ghi Nhớ Nhanh (Spaced Repetition)
Điểm vượt trội nhất của Trie so với Hash Table là gì? #card
?
Khả năng **tìm kiếm theo tiền tố (Prefix Search / `startsWith`)** cực nhanh trong thời gian $O(L)$ (phụ thuộc độ dài từ, hoàn toàn độc lập với số lượng hàng triệu từ trong từ điển).
2 ứng dụng thực tế phổ biến nhất của Trie trong phần mềm? #card
?
1. Tính năng **Tự động điền & Gợi ý từ khóa (Autocomplete / Typeahead)** của Google Search, IDE.
2. **Bộ định tuyến URL (Router Matching)** trong các Web Framework (như Gin trong Go, Express).
