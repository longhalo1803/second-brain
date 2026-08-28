---
title: Hướng dẫn Sử dụng & Quản trị Kho Tri thức Database
aliases:
  - README
  - Database Vault Guide
tags:
  - meta
  - database
  - documentation
type: reference
created: 2026-08-26
updated: 2026-08-28
---

# 🗄️ Database Knowledge Vault (Second Brain)

> Kho tri thức chuyên sâu về **Database Engine, Cơ chế Lưu trữ Vật lý, Concurrency Control & Tối ưu hóa SQL**. Tối ưu cho việc học tập theo nguyên lý gốc và tra cứu thực chiến.
>
> 📌 _Quy định chung về Frontmatter, cấu trúc Note 5 phần và quy trình nạp tri thức tuân thủ theo: [Universal Specification](../README.md#📐-5-quy-định-chung-khi-nạp-tri-thức-universal-specification)._

---

## 🗺️ 1. Bản Đồ Tri Thức Trung Tâm (Maps of Content - MOC)

Toàn bộ hệ thống ghi chú trong Vault được kết nối qua 4 MOC chuyên đề chính trong thư mục `00 - Maps of Content/`:

- 🧭 **[[MOC - Database Overview]]**: Bản đồ tổng quan toàn bộ Vault và liên kết ngoại vi.
- ⚡ **[[MOC - Query Optimization]]**: Hub tối ưu truy vấn, Execution Plan, Cost-Based Optimizer.
- 💾 **[[MOC - Storage & Engine]]**: Hub cấu trúc đĩa, Block (Page), Row ID, Buffer Cache, VACUUM.
- 🔒 **[[MOC - Concurrency & Lock]]**: Hub quản trị đồng thời, MVCC, Lock leo thang & Deadlock.

---

## 📂 2. Cấu Trúc Phân Tầng Nội Dung

```text
Database-knowledge/
├── 00 - Maps of Content/          # 4 Hub trung tâm điều hướng toàn bộ Vault
├── 01 - Core Concepts/            # Các khái niệm nguyên tử (Block, Buffer Cache, Index, Lock, Cost, Execution Plan...)
├── 02 - Core Principles/          # Nguyên lý 3+2, Tư duy Architect, Quy trình 6 bước xử lý SQL...
├── 03 - Practical & Case Studies/ # Tình huống thực chiến (Table 0 row truy vấn chậm, Lỗi index, Lock leo thang...)
├── 04 - Reference & Learning/     # Lộ trình học Database toàn diện, Bộ câu hỏi phỏng vấn...
└── 99 - Attachments/              # Quản lý tập trung
    ├── drawings/                  # Sơ đồ Excalidraw (*.excalidraw.md)
    └── images/                    # Hình ảnh minh họa cấu trúc dữ liệu đĩa
```

---

## 🏷️ 3. Metadata Đặc Thù Cho Database Vault

Khi nạp note mới vào Database Vault, sử dụng các thẻ phân loại đặc thù sau trong Frontmatter:

```yaml
---
title: Tên khái niệm / Nguyên lý Database
aliases:
  - Tên tiếng Anh (ví dụ: Buffer Cache, Deadlock, Covering Index)
  - Tên viết tắt / không dấu
tags:
  - database
  - sub-topic # Chọn: storage | optimizer | index | lock | concurrency | mvcc | execution-plan
type: concept # concept | principle | practical | case-study | moc | reference
created: YYYY-MM-DD
updated: YYYY-MM-DD
---
```

---

## 💡 4. Điểm Khởi Đầu Tra Cứu

Bắt đầu bằng việc mở:

1. 🧭 **[[MOC - Database Overview]]** để xem toàn cảnh đồ thị tri thức.
2. 📋 **[[Lộ trình học Database toàn diện cho Developer]]** để theo dõi lộ trình học tập.
3. 🎯 **[[Tư duy tối ưu Database (Database Tuning Mindset)]]** để nắm vững các nguyên lý cốt lõi.
