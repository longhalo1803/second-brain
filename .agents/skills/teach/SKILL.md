---
name: teach
description: Dạy học chuyên sâu theo Alvar Method (First Principles + Motivated Discovery + 3 pha Probe/Plan/Teach). Tối ưu cho agy CLI và Obsidian.
---

# Alvar Method Teaching System (agy CLI + Obsidian)

Hệ thống giảng dạy Socratic & Nguyên lý gốc. Mục tiêu: **Hiểu bản chất > Học vẹt**, biến kiến thức thành Đồ thị Phụ thuộc (DAG) vững chắc.

---

## 🧠 2 Nguyên Lý Cốt Lõi

1. **Chân lý vô điều kiện trước (Unconditional Truths First):** Nêu tiên đề nền tảng luôn đúng, không ngoại lệ (ví dụ: _"Mọi I/O đĩa đều đọc theo Block 4KB"_, _"Không có index nào mà không tốn chi phí ghi"_).
2. **Khám phá có động cơ (Motivated Discovery):** Dẫn dắt tư duy kiểu 3Blue1Brown (Tại sao cách ngây thơ thất bại? $\to$ Động lực ra đời giải pháp $\to$ Công thức toán $\LaTeX$).

---

## 🔄 Quy Trình 3 Pha Vận Hành

```mermaid
graph TD
    subgraph Phase 1: Probe
        P1[1a. ask_question trắc nghiệm] --> P2[1b. Xác định sàn đúng & trần hổng]
    end
    subgraph Phase 2: Plan
        P2 --> PL1[Kiểm chứng tài liệu gốc qua search_web / research]
        PL1 --> PL2[Vẽ Mermaid DAG lộ trình bài học]
        PL2 --> PL3[Cổng duyệt: ask_question xác nhận]
    end
    subgraph Phase 3: Teach Loop
        PL3 --> T1[Motivate: Tại sao cần node này?]
        T1 --> T2[Establish: Bản chất + LaTeX $...$]
        T2 --> T3[Connect: Nối vào đồ thị tri thức]
        T3 --> T4[Quiz Lock: Khóa node bằng ask_question]
        T4 -->|Đạt| T5[Auto-Sync: write_to_file lưu vào Vault]
        T5 --> T1
    end
```

---

### Pha 1: Dò Biên (Probe)

- **Bắt buộc gọi `ask_question`:** Đặt 1-2 câu trắc nghiệm chẩn đoán để định vị sàn (đã biết chắc) và trần (chỗ hổng/ngộ nhận).
- **Quy tắc câu hỏi:** Các lựa chọn có độ dài/văn phong tương đương; đáp án sai phải là ngộ nhận thực tế phổ biến; không mớm đáp án.

### Pha 2: Lập Kế Hoạch (Plan)

1. **Khử ảo giác:** Tra cứu tài liệu gốc (`search_web` hoặc subagent `research`) nếu cần đối chiếu thông số/chuẩn kỹ thuật.
2. **Trình bày lộ trình:** Vẽ sơ đồ **Mermaid DAG** từ Chân lý vô điều kiện $\to$ Khái niệm $\to$ Ứng dụng.
3. **Cổng kiểm duyệt:** Gọi `ask_question` để người học xác nhận kế hoạch trước khi bắt đầu dạy.

### Pha 3: Vòng Lặp Giảng Dạy (Teach Loop)

Thực hiện tuần tự cho từng node trên sơ đồ:

1. **Motivate:** Nêu vấn đề thực tế nếu thiếu khái niệm này.
2. **Establish:** Giải thích bản chất, công thức bắt buộc dùng $\LaTeX$ (`$O(\log N)$`, `$$...$$`).
3. **Connect:** Chỉ rõ mối liên hệ nhân quả với node trước.
4. **Quiz Lock:** Gọi `ask_question` với câu hỏi tư duy suy luận. Chỉ chuyển node khi người học trả lời đúng.
5. **Auto-Sync:** Gọi `write_to_file` xuất file Note `.md` chuẩn vào `[Tên-Vault]/01 - Core Concepts/` hoặc `[Tên-Vault]/02 - Core Principles/`. Cập nhật liên kết vào MOC tương ứng bằng `replace_file_content`.

---

## 📋 Chuẩn Định Dạng Note Obsidian

- **WikiLinks:** Bọc thuật ngữ bằng `[[Tên Khái Niệm]]`.
- **Callouts:** `> [!NOTE] Nguyên lý Nền tảng`, `> [!TIP] Trực giác Tự nhiên`.
- **LaTeX Math:** `$O(1)$`, `$$ T(n) = 2T(n/2) + O(n) $$`.
- **Mermaid:** Viết trực tiếp khối `mermaid`.
