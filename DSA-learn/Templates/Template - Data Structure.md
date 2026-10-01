---
title: "<% tp.file.title %>"
aliases:
  - "<% tp.file.title %>"
tags:
  - dsa
  - data-structure
stage: 2
type: concept
difficulty: fundamental
status: in-progress
sources:
  - "[[CLRS - Introduction to Algorithms]]"
cross_domain: []
created: <% tp.date.now("YYYY-MM-DD") %>
updated: <% tp.date.now("YYYY-MM-DD") %>
---

# 📦 <% tp.file.title %>

> [[00 - Master Dashboard|🧭 Dashboard]] / [[Master MOC|🗺️ Master MOC]] / [[Array & Dynamic Array|📦 Data Structures]]

---

## 1. Bản Chất Cốt Lõi (Mental Model)

- **Định nghĩa:**
- **Hình dung sinh động:**
- **Cách tổ chức trong bộ nhớ (Memory Layout):** _(Contiguous Array, Node Con trỏ, Hash Bucket...)_

---

## 2. Bảng Độ Phức Tạp (Complexity Sheet)

| Thao Tác (Operation)         | Thời Gian Trung Bình (Average) | Thời Gian Xấu Nhất (Worst) | Không Gian Bộ Nhớ (Space) |
| :--------------------------- | :----------------------------- | :------------------------- | :------------------------ |
| **Truy cập (Access / Read)** | `O(?)`                         | `O(?)`                     | `O(1)`                    |
| **Tìm kiếm (Search)**        | `O(?)`                         | `O(?)`                     | `O(1)`                    |
| **Chèn (Insert)**            | `O(?)`                         | `O(?)`                     | `O(1)`                    |
| **Xóa (Delete)**             | `O(?)`                         | `O(?)`                     | `O(1)`                    |

---

## 3. Sự Đánh Đổi (Trade-offs) & So Sánh Đối Trọng

- 🟢 **Ưu điểm lớn nhất (Superpower):**
- 🔴 **Nhược điểm lớn nhất (Kryptonite / Weakness):**
- ⚖️ **So sánh đối trọng:**
  - So với `Cấu trúc khác`: Khi nào nên dùng <% tp.file.title %> và khi nào nên dùng cấu trúc kia?

---

## 4. Ứng Dụng Thực Tế & Liên Kết Đa Miền (Cross-Domain Systems)

- 🗄️ **Database Engine:**
- 🌐 **Backend Protocols & System Design:**
- 🐧 **Linux Kernel / OS Virtual Memory:**

---

## 5. Mẫu Code Chuẩn (Clean TypeScript Implementation)

```typescript
class CustomDataStructure<T> {
  private items: T[];

  constructor() {
    this.items = [];
  }

  public push(item: T): void {
    this.items.push(item);
  }

  public pop(): T | undefined {
    return this.items.pop();
  }
}
```

---

## 6. Các Mẫu Bài Toán & LeetCode Điển Hình (Patterns & Problems)

- [[Two Pointers Pattern]]
- `[[Problem Example]]`

---

## 🧠 Thẻ Ghi Nhớ Nhanh (Spaced Repetition)

Điểm mạnh và điểm yếu cốt lõi của <% tp.file.title %> là gì? #card
?

- Điểm mạnh: ...
- Điểm yếu: ...
