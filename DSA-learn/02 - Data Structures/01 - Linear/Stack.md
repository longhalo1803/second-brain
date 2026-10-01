---
title: Ngăn Xếp (Stack - LIFO)
aliases:
  - Stack
  - Ngăn xếp
  - LIFO
  - Call Stack
tags:
  - dsa
  - data-structure
  - linear
stage: 2
type: concept
difficulty: fundamental
status: completed
created: 2026-08-27
updated: 2026-10-01
sources:
  - "[[CLRS - Introduction to Algorithms]]"
cross_domain:
  - "[[DevOps-knowledge/Roadmap]]"
---

# 🥞 Ngăn Xếp (Stack - LIFO)

> [[00 - Master Dashboard|🧭 Dashboard]] / [[Master MOC|🗺️ Master MOC]] / [[Roadmap|📋 Roadmap]]

---

## 1. Bản Đồ Khái Niệm (Mermaid DAG)

```mermaid
graph TD
    In["Dữ Liệu Mới (Element)"] -->|Thao tác push()| Top["Đỉnh Ngăn Xếp (Top Pointer)"]
    Top -->|Thao tác pop()| Out["Lấy Ra Phần Tử Vào Sau Cùng (LIFO)"]
    Top -->|Thao tác peek()| Check["Xem Trước Phần Tử Đỉnh $O(1)$"]
    Top --> Arch["Ứng Dụng Cốt Lõi"]
    Arch --> S1["Call Stack & Đệ Quy Hệ Điều Hành"]
    Arch --> S2["Monotonic Stack (Tìm Phần Tử Lớn Hơn Kế Tiếp)"]
    Arch --> S3["Thuật Toán Duyệt Đồ Thị DFS"]
```

---

## 2. Chân Lý Vô Điều Kiện (First Principles)

> [!NOTE] Tiên Đề Bất Biến (LIFO Principle)
> **Phần tử được nạp vào sau cùng (Last In) bắt buộc phải là phần tử đầu tiên được lấy ra (First Out).**
>
> Mọi thao tác cốt lõi trên đỉnh ngăn xếp (`push`, `pop`, `peek`) đều có độ phức tạp thời gian tuyệt đối **[[O(1) - Constant Time|$O(1)$]]**. Không cho phép truy cập ngẫu nhiên vào các phần tử ở giữa hoặc đáy ngăn xếp.

---

## 3. Trực Giác Motivated Discovery

> [!TIP] Động Lực 3Blue1Brown: Chồng Đĩa Trong Tiệc Cưới
> Khi người bồi bàn xếp đĩa sạch lên bàn ăn, từng chiếc đĩa được đặt chồng lên trên chiếc trước đó.
>
> Khi thực khách lấy đĩa ăn: Bạn chỉ có thể lấy chiếc đĩa nằm ở **trên cùng (Top)**. Muốn lấy chiếc đĩa ở đáy, bạn bắt buộc phải bốc dỡ toàn bộ các đĩa phía trên ra trước.
>
> Cấu trúc này mô phỏng hoàn hảo **lịch sử thực thi của chương trình máy tính**: Hàm `A()` gọi hàm `B()`, hàm `B()` gọi hàm `C()`. Hàm `C()` phải chạy xong và thoát ra trước thì `B()` mới tiếp tục chạy, và cuối cùng mới trở về `A()`. Đó chính là **Call Stack** trong CPU và RAM!

---

## 4. Phân Tích Kỹ Thuật & Độ Phức Tạp

### Bảng Độ Phức Tạp (Complexity Sheet)

| Thao Tác | Thời Gian (Time) | Không Gian (Space) | Ghi Chú |
| :--- | :--- | :--- | :--- |
| **`push(val)` (Đẩy vào đỉnh)** | [[O(1) - Constant Time|$O(1)$]] | [[O(1) - Constant Time|$O(1)$]] | Amortized $O(1)$ trên Mảng động |
| **`pop()` (Rút khỏi đỉnh)** | [[O(1) - Constant Time|$O(1)$]] | [[O(1) - Constant Time|$O(1)$]] | Lấy ra và xóa phần tử đỉnh |
| **`peek()` (Xem đỉnh)** | [[O(1) - Constant Time|$O(1)$]] | [[O(1) - Constant Time|$O(1)$]] | Chỉ đọc, không thay đổi Stack |
| **Tìm kiếm (Search)** | [[O(n) - Linear Time|$O(n)$]] | [[O(1) - Constant Time|$O(1)$]] | Phải bốc dỡ các phần tử phía trên |

---

## 5. Cài Đặt Chuẩn Mực (TypeScript)

```typescript
export class Stack<T> {
  private items: T[] = [];

  // Đẩy phần tử vào đỉnh Stack trong O(1)
  push(item: T): void {
    this.items.push(item);
  }

  // Rút phần tử khỏi đỉnh Stack trong O(1)
  pop(): T | undefined {
    return this.items.pop();
  }

  // Xem phần tử ở đỉnh trong O(1)
  peek(): T | undefined {
    return this.items[this.items.length - 1];
  }

  // Kiểm tra rỗng
  isEmpty(): boolean {
    return this.items.length === 0;
  }

  get size(): number {
    return this.items.length;
  }
}
```

---

## 🧠 Thẻ Ghi Nhớ Nhanh (Spaced Repetition)

Nguyên lý LIFO trong Stack là gì? #card
?
LIFO (Last In, First Out): Phần tử được thêm vào cuối cùng sẽ là phần tử đầu tiên được lấy ra khỏi cấu trúc dữ liệu. Mọi thao tác thêm/xóa chỉ diễn ra tại một đầu duy nhất gọi là đỉnh (Top).

Tại sao đệ quy vô hạn lại dẫn đến lỗi "Stack Overflow"? #card
?
Vì mỗi lần gọi hàm, hệ điều hành cấp phát một khung bộ nhớ (Stack Frame) trên Call Stack trong RAM. Nếu đệ quy không có điều kiện dừng (Base Case), Stack phình to vượt quá giới hạn bộ nhớ cho phép của tiến trình $\to$ hệ điều hành cưỡng chế hủy chương trình.
