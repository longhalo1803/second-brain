# 🤖 AGENT GUIDELINES & INSTRUCTIONS FOR `second-brain`

Repository này là một **Master Knowledge Vault** trên Obsidian (Kỹ thuật Phần mềm & AI Agent Engineering), vận hành theo phương pháp **Alvar Method (First Principles)** và hệ thống **Antigravity CLI (`agy`)**.

Mọi AI Agent khi làm việc trong workspace này BẮT BUỘC tuân thủ các quy tắc sau:

---

## 🗺️ 1. CẤU TRÚC KHO CHỨA (5 DOMAINS)

1. **`AI-knowledge/`**: AI Agents, Context RAM, RAG, LangGraph, LLMOps.
2. **`Database-knowledge/`**: Disk Storage, Buffer Cache, B+Tree, MVCC, Locks.
3. **`DSA-learn/`**: Cấu trúc dữ liệu, Giải thuật, Big-O, Mental Models.
4. **`Backend-full-course/`**: Protocols (TCP/IP, QUIC, HTTP/3), System Design.
5. **`DevOps-knowledge/`**: Linux Kernel, Docker, K8s, Terraform, Observability.

---

## 📜 2. TRIẾT LÝ HỌC TẬP (ALVAR METHOD)

- **Unconditional Truths First:** Luôn bắt đầu từ tiên đề/chân lý vô điều kiện không thể tranh cãi.
- **Motivated Discovery:** Trực giác 3Blue1Brown: _Vấn đề ngây thơ $\rightarrow$ Động lực giải pháp $\rightarrow$ Công thức $\LaTeX$_.
- **Zero Hallucination:** 100% chuẩn kỹ thuật, RFC, API signature phải tra cứu từ Official Docs.

---

## 📝 3. QUY CHUẨN ĐỊNH DẠNG NOTE (.md)

### 3.1. Frontmatter Bắt Buộc

```yaml
---
title: Tên bài viết đầy đủ
aliases:
  - Tên tiếng Anh chuẩn
  - Viết tắt / Từ đồng nghĩa
tags:
  - domain (ai, database, dsa, backend, devops)
  - sub-topic
type: concept | principle | practical | pattern | moc | reference
status: completed | in-progress | review-needed
created: YYYY-MM-DD
updated: YYYY-MM-DD
---
```

### 3.2. Cấu Trúc Note 5 Phần

1. **Mermaid DAG Phụ thuộc**: Cấu trúc liên kết khái niệm.
2. **Chân lý vô điều kiện**: Đặt trong Callout `> [!NOTE]`.
3. **Trực giác Motivated Discovery**: Đặt trong Callout `> [!TIP]`.
4. **Phân tích kỹ thuật & $\LaTeX$**: Chi tiết cơ chế, toán học ($O(\log N)$).
5. **Flashcards & WikiLinks**: Spaced Repetition (`#card`) và liên kết 2 chiều (`[[...]]`).

### 3.3. Cấu Trúc Thư Mục Trong Mỗi Module

- `00 - Maps of Content/`
- `01 - Core Concepts/`
- `02 - Core Principles/`
- `03 - Practical & Case Studies/`
- `04 - Reference & Learning/`
- `99 - Attachments/` _(Bản vẽ Excalidraw lưu tại `Excalidraw/` ở root)_

---

## 🛠️ 4. SKILLS NỘI BỘ DỰ ÁN (.agents/skills/)

- **`research`** (`.agents/skills/research/SKILL.md`): Tra cứu Official Docs/RFCs khử 100% ảo giác.
- **`teach`** (`.agents/skills/teach/SKILL.md`): Giảng dạy Socratic 3 pha (Probe $\rightarrow$ Plan $\rightarrow$ Teach Loop với Quiz Lock).
- **`visualize`** (`.agents/skills/visualize/SKILL.md`): Trực quan hóa sơ đồ Mermaid, Excalidraw, SVG.

---

## 🎯 5. QUY CHUẨN TRẮC NGHIỆM (`ask_question`)

1. **Tối thiểu 4 lựa chọn ($\ge 4$ Options)**.
2. **Ngẫu nhiên hóa đáp án đúng**: CẤM tuyệt đối luôn đặt đáp án đúng ở Option 1.
3. **KHÔNG bao giờ** thêm tiền tố `(Recommended)`.
4. **Đáp án nhiễu tinh vi**: Phản ánh ngộ nhận thực tế.
5. **Đồng nhất văn phong & độ dài**.
