---
title: Sắp Xếp Nổi Bọt (Bubble Sort)
aliases:
  - Bubble Sort
  - Sắp xếp nổi bọt
tags:
  - dsa
  - algorithm
  - sorting
stage: 3
type: concept
difficulty: fundamental
status: completed
created: 2026-08-27
updated: 2026-10-01
sources:
  - "[[CLRS - Introduction to Algorithms]]"
cross_domain: []
---

# 🫧 Sắp Xếp Nổi Bọt (Bubble Sort)

> [[00 - Master Dashboard|🧭 Dashboard]] / [[Master MOC|🗺️ Master MOC]] / [[Roadmap|📋 Roadmap]]

---

## 1. Bản Đồ Khái Niệm (Mermaid DAG)

```mermaid
graph TD
    A["Mảng Đầu Vào Chưa Sắp Xếp"] --> B["So Sánh Cặp Liền Kề: arr[i] > arr[i+1]"]
    B -->|Sai Thứ Tự| C["Hoán Đổi (Swap) Tại Chỗ"]
    B -->|Đúng Thứ Tự| D["Bỏ Qua, Duyệt Cặp Kế"]
    C --> E["Phần Tử Lớn Nhất 'Nổi Bọt' Về Cuối"]
    D --> E
    E --> F{"Còn Cặp Nào Cần Hoán Đổi?"}
    F -->|Có| B
    F -->|Không (swapped = false)| G["Mảng Đã Sắp Xếp Tuyệt Đối"]
```

---

## 2. Chân Lý Vô Điều Kiện (First Principles)

> [!NOTE] Tiên Đề Bất Biến
> **Sau mỗi vòng lặp ngoài thứ $k$, đúng $k$ phần tử lớn nhất đã được đưa về chính xác vị trí cuối cùng của chúng.**
>
> 1. Bubble Sort là thuật toán **so sánh tại chỗ (In-place Comparison)**: Không cần cấp phát thêm bất kỳ mảng phụ nào ($O(1)$ Auxiliary Space).
> 2. Bubble Sort có tính **Ổn định (Stable)**: Hai phần tử có giá trị bằng nhau sẽ không bao giờ bị hoán đổi vị trí qua lại (`arr[i] > arr[i+1]` chứ không phải `>=`).

---

## 3. Trực Giác Motivated Discovery

> [!TIP] Động Lực 3Blue1Brown: Bong Bóng Trong Bể Nước
> Hãy tưởng tượng các số là những quả bóng chứa không khí dưới đáy hồ nước: quả bóng to hơn (giá trị lớn hơn) sẽ có lực đẩy nổi lớn hơn và từ từ đẩy các quả bóng nhỏ hơn xuống dưới để vươn lên mặt nước.
>
> Bằng cách chỉ thực hiện **so sánh cục bộ giữa 2 phần tử sát sườn**, ta đảm bảo phần tử "nặng" nhất luôn bị đẩy dạt dần về biên phải sau mỗi lượt quét. Nếu sau cả một lượt quét mà không có bất kỳ quả bóng nào phải đổi chỗ, ta kết luận toàn bộ mặt hồ đã phẳng lặng (mảng đã sắp xếp xong $\to$ dừng sớm).

---

## 4. Phân Tích Kỹ Thuật & Độ Phức Tạp

### Bảng Độ Phức Tạp (Complexity Sheet)

| Trường Hợp | Thời Gian (Time) | Không Gian (Space) | Điều Kiện Kích Hoạt |
| :--- | :--- | :--- | :--- |
| **Tốt nhất (Best Case)** | [[O(n) - Linear Time|$O(n)$]] | [[O(1) - Constant Time|$O(1)$]] | Mảng đã sắp xếp sẵn + có cờ tối ưu `swapped`. |
| **Trung bình (Average)** | [[O(n^2) - Quadratic Time|$O(n^2)$]] | [[O(1) - Constant Time|$O(1)$]] | Dữ liệu ngẫu nhiên, số phép đổi chỗ $\approx \frac{n(n-1)}{4}$. |
| **Xấu nhất (Worst Case)** | [[O(n^2) - Quadratic Time|$O(n^2)$]] | [[O(1) - Constant Time|$O(1)$]] | Mảng bị đảo ngược hoàn toàn ($n(n-1)/2$ phép so sánh). |

---

## 5. Cài Đặt Chuẩn Mực (TypeScript & Python)

### TypeScript (Tối ưu với Cờ `swapped`)

```typescript
export function bubbleSort(arr: number[]): number[] {
  const n = arr.length;
  let swapped: boolean;

  for (let i = 0; i < n - 1; i++) {
    swapped = false;

    // Sau mỗi vòng i, i phần tử cuối đã đúng vị trí, không cần duyệt lại
    for (let j = 0; j < n - 1 - i; j++) {
      if (arr[j] > arr[j + 1]) {
        // Hoán đổi tại chỗ
        [arr[j], arr[j + 1]] = [arr[j + 1], arr[j]];
        swapped = true;
      }
    }

    // Nếu không có hoán đổi nào xảy ra trong lượt duyệt, mảng đã sắp xếp xong
    if (!swapped) break;
  }

  return arr;
}
```

---

## 🧠 Thẻ Ghi Nhớ Nhanh (Spaced Repetition)

Làm thế nào để tối ưu Bubble Sort đạt độ phức tạp thời gian $O(n)$ trong trường hợp tốt nhất? #card
?
Sử dụng một cờ hiệu boolean `swapped`. Trước mỗi lượt duyệt trong gán `swapped = false`. Nếu có hoán đổi thì gán `swapped = true`. Sau vòng lặp trong, nếu `swapped` vẫn là `false`, nghĩa là không còn nghịch thế $\to$ `break` dừng thuật toán ngay lập tức.

Tại sao Bubble Sort không bao giờ được sử dụng trong các hệ thống phần mềm thực tế? #card
?
Vì độ phức tạp trung bình và xấu nhất của nó là $O(n^2)$, với số lượng phép ghi/hoán đổi bộ nhớ quá lớn so với [[Quick Sort]] ($O(n \log n)$) hay [[Merge Sort]] ($O(n \log n)$).
