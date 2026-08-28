# Learning Record 0002: Context RAM & Payload Assembly (First Principles)

- **Date**: 2026-08-26
- **Topic**: Bản chất vật lý và luồng dữ liệu của Context RAM trong AI Agent
- **Methodology**: First Principles Thinking (Nguyên lý đầu tiên)

## 1. Bản chất cốt lõi (Ground Truths)
1. **LLM là Hàm toán học không trạng thái (Stateless Function)**:
   $$y = f(x)$$
   LLM không có bộ nhớ động giữ lại giữa các API calls. Nó chỉ nhận một chuỗi Tokens đầu vào $x$ và tính toán xác suất sinh token tiếp theo.
2. **Context RAM không phải một thực thể phần cứng hay "trí tuệ con"**:
   Đây là **thuật ngữ ẩn dụ** đại diện cho **Payload văn bản có cấu trúc** (JSON Array / Prompt String) được tổng hợp từ nhiều nguồn dữ liệu trước khi gửi sang cho LLM.
3. **Quá trình "xào nấu" (Reasoning / Fusion)** không diễn ra ở tầng Context RAM, mà diễn ra tại **Cơ chế Self-Attention** trên GPU của LLM Provider.

## 2. Phân định vị trí thực thi (Execution Topology)
- **Tầng Agent Runtime / Orchestrator**:
  - Chạy ở **Local User Machine** (nếu dùng CLI như Claude Code, Antigravity, local Python app) HOẶC **Cloud Backend** của sản phẩm (nếu dùng ChatGPT Web, Perplexity).
  - Nhiệm vụ: Đọc file `SKILL.md` (Procedural), truy vấn Vector DB (Semantic), truy vấn SQL (Episodic), lấy User input. Sau đó nối chuỗi (String Concatenation / Template Injection).
- **Tầng LLM Provider**:
  - Chạy ở Data Center của OpenAI, Anthropic, Google, v.v. (hoặc máy local nếu dùng Ollama/vLLM).
  - Nhận chuỗi JSON qua HTTP POST `/v1/chat/completions`, biến đổi chuỗi thành Vector Embeddings và chạy ma trận Attention.

## 3. Cấu trúc Payload thực tế mà LLM "hứng"
```json
[
  {
    "role": "system",
    "content": "=== PROCEDURAL SKILLS ===\n[Nội dung SKILL.md]\n\n=== SEMANTIC MEMORY (DURABLE FACTS) ===\n[Kết quả RAG Top-K]\n\n=== EPISODIC LOGS ===\n[Kết quả SQL Query]"
  },
  {
    "role": "user",
    "content": "Lịch sử chat gần nhất + Câu hỏi hiện tại của người dùng"
  }
]
```

## 4. Key Takeaways
- Agent Harness là **người thợ lắp ráp** (Assembly line).
- Context RAM là **kiện hàng đã đóng gói** (The Assembled Payload).
- LLM Inference là **nhà máy xử lý** (Transformer Attention Matrix).
