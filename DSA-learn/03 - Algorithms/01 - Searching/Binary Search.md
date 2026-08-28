---
tags:
  - dsa
  - algorithm
  - searching
stage: 3
type: algorithm
status: completed
created: 2026-08-27
updated: 2026-08-27
aliases:
  - Binary Search
  - Tìm kiếm nhị phân
  - Thuật toán tìm kiếm nhị phân (Binary Search)
---

# 🔍 Tìm Kiếm Nhị Phân (Binary Search)

> [[00 - Master Dashboard|🧭 Dashboard]] / [[Master MOC|🗺️ Master MOC]] / [[Roadmap|📋 Roadmap]]

---

## 1. Bản Chất Cốt Lõi (Mental Model)
- **Mục tiêu:** Tìm vị trí của phần tử mục tiêu (Target) trong một mảng **đã được sắp xếp** với thời gian siêu tốc [[O(log n) - Logarithmic Time\|$O(\log n)$]].
- **Ý tưởng:** So sánh Target với phần tử nằm ở chính giữa mảng (`mid`):
  - Nếu `arr[mid] == target`: Tìm thấy ngay!
  - Nếu `target < arr[mid]`: Loại bỏ toàn bộ nửa bên phải, co vùng tìm kiếm về `[left, mid - 1]`.
  - Nếu `target > arr[mid]`: Loại bỏ toàn bộ nửa bên trái, co vùng tìm kiếm về `[mid + 1, right]`.

---

## 2. Bảng Độ Phức Tạp

| Độ Phức Tạp | Giá Trị | Giải Thích |
| :--- | :--- | :--- |
| **Thời gian tốt nhất (Best Case)** | [[O(1) - Constant Time\|$O(1)$]] | Trúng ngay phần tử ở giữa ở bước đầu |
| **Thời gian trung bình & xấu nhất** | [[O(log n) - Logarithmic Time\|$O(\log n)$]] | Mỗi bước loại bỏ được $50\%$ dữ liệu |
| **Không gian bộ nhớ (Space)** | [[O(1) - Constant Time\|$O(1)$]] | Dùng 2 con trỏ `left`, `right` (vòng lặp) |

---

## 3. Khuôn Mẫu Code Chuẩn (Template Tránh Lỗi Tràn Số)

```typescript
function binarySearch(nums: number[], target: number): number {
    let left = 0;
    let right = nums.length - 1;
    
    while (left <= right) {
        // Tránh lỗi tràn số nguyên (Integer Overflow) khi left + right vượt 2^31 - 1
        const mid = left + Math.floor((right - left) / 2);
        
        if (nums[mid] === target) {
            return mid;
        } else if (nums[mid] < target) {
            left = mid + 1;
        } else {
            right = mid - 1;
        }
    }
    
    return -1; // Không tìm thấy
}
```

---

## 4. Các Biến Thể Nâng Cao & Binary Search Trên Kết Quả (BS on Answer)
- Tìm vị trí xuất hiện đầu tiên (First Occurrence / `lower_bound`).
- Tìm vị trí chèn phần tử (Search Insert Position).
- **Binary Search on Answer Range:** Tìm giá trị tối ưu nhỏ nhất/lớn nhất thỏa mãn điều kiện (VD: Bài toán chia kẹo, vận chuyển hàng hóa Koko Eating Bananas).

---

## 🧠 Thẻ Ghi Nhớ Nhanh (Spaced Repetition)
Điều kiện tiên quyết bắt buộc để áp dụng Binary Search là gì? #card
?
Tập dữ liệu đầu vào **bắt buộc phải được sắp xếp trước** theo thứ tự (hoặc có tính chất đơn điệu Monotonicity).
Tại sao nên viết `mid = left + (right - left) // 2` thay vì `(left + right) // 2`? #card
?
Để **tránh lỗi tràn số nguyên (Integer Overflow)** trong các ngôn ngữ có kiểu int cố định (như Java, C++, Go) khi `left + right` vượt quá giá trị $2^{31} - 1$.
