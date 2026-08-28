---
tags:
  - meta
  - dsa
  - dashboard
  - moc
type: dashboard
status: completed
created: 2026-08-27
updated: 2026-08-27
---

# 🧭 DSA Master Learning Hub & Dashboard

> *"Đừng học thuộc lòng dòng code. Hãy xây dựng mô hình tư duy (Mental Model), thấu hiểu sự đánh đổi (Trade-offs) và nắm chắc kiến trúc tổ chức dữ liệu."*

---

## 🗺️ Bản Đồ Điều Hướng Lộ Trình (6 Giai Đoạn)

| Giai Đoạn | Chủ Đề Trọng Tâm | Hub / MOC | Trạng Thái |
| :--- | :--- | :--- | :--- |
| **Giai đoạn 1** | Nền tảng Tư duy & Thước đo Big O | [[Big-O Notation - MOC\|⚡ Big-O & Complexity MOC]] | 🟢 Hoàn thành |
| **Giai đoạn 2** | Cấu trúc Dữ liệu Tuyến tính (Linear DS) | [[Array & Dynamic Array\|📦 Linear Data Structures]] | 🟡 Đang học |
| **Giai đoạn 3** | Thuật toán cốt lõi & Kỹ thuật Lập trình | [[Binary Search\|🔍 Core Algorithms]] | ⚪ Kế hoạch |
| **Giai đoạn 4** | Kiến trúc tối ưu Tìm kiếm & Phân cấp | [[Hash Table & HashSet\|🌳 Hash, Trees & Trie]] | ⚪ Kế hoạch |
| **Giai đoạn 5** | Các Mẫu Thuật toán Thực chiến (Patterns) | [[Two Pointers Pattern\|🎯 Algorithmic Patterns]] | ⚪ Kế hoạch |
| **Giai đoạn 6** | Cấu trúc Hệ thống Chuyên sâu (Architect) | [[Trade-offs & System Architecture Decisions\|🏛️ System & Advanced DS]] | ⚪ Kế hoạch |

👉 **Xem chi tiết toàn bộ lộ trình:** [[Roadmap|📋 Lộ trình Chi tiết DSA]] | [[Master MOC|🗺️ Master MOC]]

---

## 📊 Tổng Quan Tiến Độ Học Tập (Dataview)

```dataview
TABLE type AS "Loại Note", stage AS "Giai đoạn", status AS "Trạng thái", updated AS "Cập nhật"
FROM ""
WHERE file.name != "00 - Master Dashboard" AND type != null
SORT stage ASC, file.name ASC
```

---

## ⚡ Bảng Tra Nhanh Độ Phức Tạp (Big-O Cheatsheet)

| Mức Độ | Ký Hiệu | Note Chi Tiết | Bản Chất Mental Model | Dữ Liệu $N=10^6$ |
| :--- | :--- | :--- | :--- | :--- |
| 🟢 Tuyệt đối | $O(1)$ | [[O(1) - Constant Time\|Constant Time]] | Bấm công tắc đèn, lấy hạt đậu đúng ô | 1 phép tính |
| 🟢 Rất nhanh | $O(\log n)$ | [[O(log n) - Logarithmic Time\|Logarithmic Time]] | Xé đôi cuốn từ điển sau mỗi bước | ~20 phép tính |
| 🟡 Tuyến tính | $O(n)$ | [[O(n) - Linear Time\|Linear Time]] | Mò kim đáy bể, duyệt từng phần tử | $10^6$ phép tính |
| 🟠 Tựa tuyến tính | $O(n \log n)$ | [[O(n log n) - Linearithmic Time\|Linearithmic Time]] | Tiêu chuẩn vàng của sắp xếp | $\approx 2 \times 10^7$ |
| 🔴 Bậc hai | $O(n^2)$ | [[O(n^2) - Quadratic Time\|Quadratic Time]] | Bắt tay chéo toàn bộ căn phòng | $10^{12}$ (Quá tải!) |
| ☠️ Lũy thừa | $O(2^n)$ | [[O(2^n) - Exponential Time\|Exponential Time]] | Tung đồng xu, đoán mật khẩu thô | Không khả thi |
| ☢️ Giai thừa | $O(n!)$ | [[O(n!) - Factorial Time\|Factorial Time]] | Hoán vị chỗ ngồi xe buýt | Sụp đổ hệ thống |

---

## 🧠 Thẻ Cần Ôn Tập (Spaced Repetition & Flashcards)

> [!TIP]
> Sử dụng plugin `Spaced Repetition` để tự kiểm tra kiến thức hàng ngày. Mỗi note đều có các câu hỏi Active Recall & Mental Model.

```dataview
TABLE status AS "Trạng thái", tags AS "Tags"
FROM #dsa
WHERE status = "in-progress" OR status = "backlog"
SORT updated DESC
LIMIT 10
```

---

## 🛠️ Công Cụ & Mẫu Tạo Ghi Chú Nhanh (Templates)

Khi tạo kiến thức mới, sử dụng **Templater** với các mẫu chuẩn hóa:
- 📄 [[Template - Data Structure|Mẫu Note: Cấu trúc dữ liệu]]
- 📄 [[Template - Algorithm|Mẫu Note: Thuật toán]]
- 📄 [[Template - Algorithmic Pattern|Mẫu Note: Mẫu thuật toán (Patterns)]]
- 📄 [[Template - LeetCode Problem|Mẫu Note: Giải bài tập LeetCode]]
