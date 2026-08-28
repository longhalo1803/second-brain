---
tags:
  - dsa
  - pattern
  - coding-pattern
stage: 5
type: pattern
status: in-progress
created: <% tp.date.now("YYYY-MM-DD") %>
updated: <% tp.date.now("YYYY-MM-DD") %>
aliases:
  - "<% tp.file.title %>"
---

# 🎯 <% tp.file.title %>

> [[00 - Master Dashboard|🧭 Dashboard]] / [[Master MOC|🗺️ Master MOC]] / [[Two Pointers Pattern|🎯 Patterns]]

---

## 1. Bản Chất Mẫu (Mental Model & Core Concept)
- **Ý tưởng cốt lõi:** 
- **Mục tiêu tối ưu:** Giảm độ phức tạp từ $O(n^2) \to O(n)$ bằng cách nào?
- **Hình dung trực quan:** 

---

## 2. Khi Nào Nên Áp Dụng (Pattern Triggers & Keywords)
- Đề bài yêu cầu tìm: *(Chuỗi con liên tiếp, cặp phần tử, dãy tăng dần, tối ưu dung lượng...)*
- Cấu trúc dữ liệu liên quan: *(Array, String, Linked List, Matrix...)*
- Tín hiệu nhận biết:

---

## 3. Các Biến Thể Của Pattern (Pattern Variations)
1. **Biến thể 1:** 
2. **Biến thể 2:** 

---

## 4. Khuôn Mẫu Code Chuẩn (TypeScript Boilerplate)

```typescript
function patternTemplate<T>(arr: T[]): number {
    let left = 0;
    let result = 0;
    
    for (let right = 0; right < arr.length; right++) {
        // 1. Mở rộng / Cập nhật trạng thái tại vị trí right
        
        // 2. Thu hẹp từ bên trái khi vi phạm điều kiện
        while (/* conditionViolated */ false) {
            left++;
        }
        
        // 3. Cập nhật kết quả tối ưu
        result = Math.max(result, right - left + 1);
    }
    
    return result;
}
```

---

## 5. Danh Sách Bài Tập Thực Chiến (LeetCode Top Pick)

| Bài Tập | Mức Độ | Trọng Tâm / Biến Thể | Ghi Chú Lời Giải |
| :--- | :--- | :--- | :--- |
| `[[Problem 1]]` | 🟢 Easy | Cơ bản | `Link` |
| `[[Problem 2]]` | 🟡 Medium | Nâng cao | `Link` |

---

## 🧠 Thẻ Ghi Nhớ Nhanh (Spaced Repetition)
Dấu hiệu nhận biết bài toán cần áp dụng <% tp.file.title %> là gì? #card
?
- Dấu hiệu: ...
- Cách tiếp cận: ...
