---
tags:
  - dsa
  - pattern
  - sliding-window
stage: 5
type: pattern
status: completed
created: 2026-08-27
updated: 2026-08-27
aliases:
  - Sliding Window
  - Cửa sổ trượt
  - Cửa sổ trượt (Sliding Window)
---

# 🪟 Kỹ Thuật Cửa Sổ Trượt (Sliding Window Pattern)

> [[00 - Master Dashboard|🧭 Dashboard]] / [[Master MOC|🗺️ Master MOC]] / [[Roadmap|📋 Roadmap]]

---

## 1. Bản Chất Cốt Lõi (Mental Model)
- **Mục tiêu:** Tối ưu các bài toán tìm kiếm trên **dãy con liên tiếp (contiguous subarray / substring)** từ $O(n^2)$ hoặc $O(n \cdot k)$ xuống [[O(n) - Linear Time\|$O(n)$]].
- **Ý tưởng:** Duy trì một "cửa sổ" `[left..right]` trượt dần trên mảng:
  - Khi dịch chuyển cửa sổ sang phải 1 bước: Ta chỉ cần **cộng thêm phần tử mới bước vào** và **trừ đi phần tử vừa trượt ra khỏi cửa sổ**, thay vì phải tính toán lại toàn bộ các phần tử bên trong từ đầu.
- **2 Dạng chính:**
  1. **Cửa sổ cố định (Fixed Window Size $K$):** Tìm tổng lớn nhất của $K$ phần tử liên tiếp.
  2. **Cửa sổ động (Dynamic / Variable Window):** Tìm chuỗi con dài nhất không chứa ký tự trùng lặp, hoặc mảng con ngắn nhất có tổng $\ge S$.

---

## 2. Khuôn Mẫu Code Chuẩn (Template Cửa Sổ Động)

```typescript
function dynamicSlidingWindow(s: string): number {
    let left = 0;
    let maxLen = 0;
    const charMap = new Map<string, number>(); // Lưu tần suất hoặc vị trí ký tự
    
    for (let right = 0; right < s.length; right++) {
        // 1. Nạp phần tử mới vào cửa sổ (Mở rộng bên phải)
        const char = s[right];
        charMap.set(char, (charMap.get(char) || 0) + 1);
        
        // 2. Co hẹp cửa sổ từ bên trái nếu vi phạm điều kiện
        while (/* conditionViolated */ false) {
            const leftChar = s[left];
            charMap.set(leftChar, charMap.get(leftChar)! - 1);
            left++;
        }
        
        // 3. Cập nhật kết quả tối ưu
        maxLen = Math.max(maxLen, right - left + 1);
    }
    
    return maxLen;
}
```

---

## 🧠 Thẻ Ghi Nhớ Nhanh (Spaced Repetition)
Dấu hiệu nhận biết bài toán cần áp dụng Sliding Window là gì? #card
?
Khi đề bài yêu cầu tìm kiếm, đếm hoặc tính toán trên một **dãy con liên tiếp (Contiguous Subarray / Substring)** lớn nhất, nhỏ nhất hoặc thỏa mãn một điều kiện số lượng.
Tại sao Sliding Window lại có độ phức tạp thời gian $O(n)$ dù có 2 vòng lặp (vòng `for` và `while`)? #card
?
Vì mỗi phần tử chỉ được con trỏ `right` thêm vào cửa sổ đúng 1 lần và con trỏ `left` loại bỏ khỏi cửa sổ tối đa 1 lần $\to$ Tổng số thao tác tối đa là $2n = O(n)$.
