---
title: Tìm Kiếm Tuyến Tính (Linear Search)
aliases:
  - Linear Search
  - Sequential Search
  - Tìm kiếm tuyến tính
  - Tìm kiếm tuần tự
tags:
  - dsa
  - algorithm
  - searching
stage: 3
type: concept
difficulty: fundamental
status: completed
created: 2026-08-27
updated: 2026-10-01
sources:
  - "[[CLRS - Introduction to Algorithms]]"
cross_domain:
  - "[[Database-knowledge/01 - Core Concepts/Data Access Methods]]"
---

# 🔍 Tìm Kiếm Tuyến Tính (Linear Search)

> [[00 - Master Dashboard|🧭 Dashboard]] / [[Master MOC|🗺️ Master MOC]] / [[Roadmap|📋 Roadmap]]

---

## 1. Bản Đồ Khái Niệm (Mermaid DAG)

```mermaid
graph TD
    In["Mảng / Danh Sách Dữ Liệu Bất Kỳ (Chưa Cần Sắp Xếp)"] --> Loop["Bắt Đầu Từ Phần Tử Đầu Tiên: i = 0"]
    Loop --> Comp{"arr[i] === Target?"}
    Comp -->|Đúng (Trúng Mục Tiêu)| Found["Trả Về Chỉ Số i Ngay Lập Tức: Best Case O(1)"]
    Comp -->|Sai| Inc["Chuyển Sang Phần Tử Kế Tiếp: i = i + 1"]
    Inc --> Check{"Đã Quét Hết Mảng? (i === n)"}
    Check -->|Chưa| Comp
    Check -->|Rồi (Không Thấy)| NotFound["Trả Về -1: Worst Case O(n) Tuyến Tính"]
```

---

## 2. Chân Lý Vô Điều Kiện (First Principles)

> [!NOTE] Tiên Đề Giới Hạn Dưới Khi Thiếu Thông Tin Tiên Nghiệm
> **Nếu dữ liệu đầu vào chưa được sắp xếp và không có bất kỳ cấu trúc chỉ mục phụ trợ nào (Index/Hash), không tồn tại thuật toán nào có thể tìm kiếm nhanh hơn thời gian tuyến tính $\Omega(n)$.**
>
> 1. **Thuật toán phổ quát tuyệt đối:** Linear Search hoạt động trên **mọi cấu trúc dữ liệu tuyến tính**: từ mảng ngẫu nhiên, chuỗi ký tự, đến [[Linked List|Danh sách liên kết]] (nơi [[Binary Search]] hoàn toàn bất lực do không có $O(1)$ Random Access).
> 2. **Ưu thế trên tập dữ liệu nhỏ ($N \le 16$):** Nhờ việc truy cập các ô nhớ liên tiếp kích hoạt tính năng **Hardware Prefetching** của CPU, Linear Search trên mảng nhỏ chạy nhanh hơn Binary Search vì không tốn chi phí rẽ nhánh và phép chia `mid`.

---

## 3. Trực Giác Motivated Discovery

> [!TIP] Động Lực 3Blue1Brown: Mò Chìa Khóa Trong Túi Quần Tối Om
> Bạn thò tay vào chiếc túi chứa 10 chiếc chìa khóa lộn xộn trong đêm tối. Bạn không biết chiếc nào mở được cửa:
>
> Bạn buộc phải bốc chiếc đầu tiên thử vào ổ. Không vừa $\to$ bốc chiếc thứ 2 $\to$ chiếc thứ 3... Chiếc chìa khóa đúng có thể nằm ngay trên đầu (bạn ăn may trong 1 giây - Best Case $O(1)$), nhưng cũng có thể nằm ở đáy túi, buộc bạn phải thử hết toàn bộ 10 chiếc (Worst Case $O(n)$).

---

## 4. Phân Tích Kỹ Thuật & Đa Miền Hệ Thống

### Bảng Độ Phức Tạp (Complexity Sheet)

| Trường Hợp | Thời Gian (Time) | Không Gian (Space) | Điều Kiện |
| :--- | :--- | :--- | :--- |
| **Tốt nhất (Best Case)** | [[O(1) - Constant Time|$O(1)$]] | [[O(1) - Constant Time|$O(1)$]] | Phần tử cần tìm nằm ngay tại vị trí `arr[0]` |
| **Trung bình (Average)** | [[O(n) - Linear Time|$O(n)$]] | [[O(1) - Constant Time|$O(1)$]] | Duyệt trung bình khoảng $n / 2$ phần tử |
| **Xấu nhất (Worst Case)** | [[O(n) - Linear Time|$O(n)$]] | [[O(1) - Constant Time|$O(1)$]] | Phần tử nằm ở cuối mảng hoặc không tồn tại |

### 🌐 Liên Kết Đa Miền: Full Table Scan Trong Database
Trong Cơ sở dữ liệu, khi bảng không có [[Database-knowledge/01 - Core Concepts/Index|B+Tree Index]] trên cột tìm kiếm, Database Engine (PostgreSQL / MySQL) buộc phải thực hiện **[[Database-knowledge/01 - Core Concepts/Data Access Methods|Full Table Scan (Quét toàn bộ bảng)]]**. Đây chính là hiện thân của Linear Search ở tầng Disk Block I/O.

---

## 5. Cài Đặt Chuẩn Mực (TypeScript)

### 1. Cài đặt cơ bản

```typescript
export function linearSearch<T>(arr: T[], target: T): number {
  for (let i = 0; i < arr.length; i++) {
    if (arr[i] === target) {
      return i; // Tìm thấy mục tiêu tại vị trí i
    }
  }
  return -1; // Không tìm thấy
}
```

### 2. Kỹ thuật tối ưu "Lính Canh" (Sentinel Linear Search)
Kỹ thuật này đặt mục tiêu vào cuối mảng để **triệt tiêu phép so sánh biên vòng lặp `i < arr.length`**, giúp giảm $50\%$ số lượng phép so sánh điều kiện:

```typescript
export function sentinelLinearSearch(arr: number[], target: number): number {
  const n = arr.length;
  if (n === 0) return -1;

  const last = arr[n - 1];
  // Đặt lính canh ở cuối mảng
  arr[n - 1] = target;

  let i = 0;
  // Không cần kiểm tra i < n trong vòng lặp!
  while (arr[i] !== target) {
    i++;
  }

  // Khôi phục lại giá trị gốc
  arr[n - 1] = last;

  if (i < n - 1 || last === target) {
    return i;
  }
  return -1;
}
```

---

## 🧠 Thẻ Ghi Nhớ Nhanh (Spaced Repetition)

Khi nào bắt buộc phải dùng Linear Search thay vì Binary Search? #card
?
1. Khi tập dữ liệu **chưa được sắp xếp** và chi phí sắp xếp $O(n \log n)$ lớn hơn chi phí tìm kiếm $O(n)$.
2. Khi dữ liệu được lưu trên cấu trúc không hỗ trợ truy xuất ngẫu nhiên $O(1)$ như [[Linked List|Danh sách liên kết]].

Kỹ thuật "Lính canh" (Sentinel Search) giúp tối ưu hóa Linear Search như thế nào? #card
?
Nó gán giá trị cần tìm vào cuối mảng làm điểm dừng cưỡng bức, giúp loại bỏ điều kiện kiểm tra biên `i < n` ở mỗi bước lặp của vòng `while`, giảm một nửa số phép so sánh rẽ nhánh của CPU.
