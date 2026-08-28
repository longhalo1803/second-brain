---
tags:
  - dsa
  - pattern
  - two-pointers
stage: 5
type: pattern
status: completed
created: 2026-08-27
updated: 2026-08-27
aliases:
  - Two Pointers
  - Hai con trỏ
  - Hai con trỏ (Two Pointers)
---

# 👥 Kỹ Thuật Hai Con Trỏ (Two Pointers Pattern)

> [[00 - Master Dashboard|🧭 Dashboard]] / [[Master MOC|🗺️ Master MOC]] / [[Roadmap|📋 Roadmap]]

---

## 1. Bản Chất Cốt Lõi (Mental Model)
- **Mục tiêu:** Giảm độ phức tạp thời gian từ [[O(n^2) - Quadratic Time\|$O(n^2)$]] xuống [[O(n) - Linear Time\|$O(n)$]] với không gian bộ nhớ [[O(1) - Constant Time\|$O(1)$]] bằng cách sử dụng **2 biến chỉ số (pointers)** duyệt mảng đồng thời.
- **2 Dạng chính:**
  1. **Đối đầu (Opposite Direction):** Con trỏ `Left` ở đầu mảng, con trỏ `Right` ở cuối mảng, di chuyển lại gần nhau (áp dụng trên mảng đã sắp xếp, bài toán Palindrome, Two Sum II).
  2. **Cùng chiều (Fast & Slow Pointers):** Con trỏ nhanh đi trước, con trỏ chậm đi sau (áp dụng tìm chu trình trong [[Linked List|Linked List - Floyd's Cycle Detection]], loại bỏ phần tử trùng lặp tại chỗ).

---

## 2. Khuôn Mẫu Code Chuẩn (Template Hai Con Trỏ Đối Đầu)

```typescript
function twoSumSorted(nums: number[], target: number): number[] {
    let left = 0;
    let right = nums.length - 1;
    
    while (left < right) {
        const currentSum = nums[left] + nums[right];
        if (currentSum === target) {
            return [left, right];
        } else if (currentSum < target) {
            left++; // Cần tổng lớn hơn -> dịch con trỏ trái sang phải
        } else {
            right--; // Cần tổng nhỏ hơn -> dịch con trỏ phải sang trái
        }
    }
    
    return [];
}
```

---

## 🧠 Thẻ Ghi Nhớ Nhanh (Spaced Repetition)
Khi nào nên nghĩ ngay đến kỹ thuật Two Pointers đối đầu? #card
?
Khi bài toán thao tác trên một **Mảng / Chuỗi đã được sắp xếp** (hoặc bài toán đối xứng Palindrome) và yêu cầu tìm một cặp phần tử thỏa mãn điều kiện với bộ nhớ tối ưu **$O(1)$ Space**.
Thuật toán Floyd's Tortoise and Hare (Rùa và Thỏ) áp dụng Fast & Slow Pointers để làm gì? #card
?
Để phát hiện **Chu trình trong Linked List (Cycle Detection)** hoặc tìm **Nút chính giữa (Middle Node)** của Linked List chỉ trong 1 lần duyệt $O(n)$ Time và $O(1)$ Space.
