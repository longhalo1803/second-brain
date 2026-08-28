# Learning Record 0001: AI Agent Harness & Loop Engineering

- **Date**: 2026-08-26
- **Source**: [YouTube: Sean - AI Agent Harness & Loop Engineering](https://youtu.be/GrNbuWWJYiI)
- **Status**: Completed

## 1. Core Paradigm: The Horse & The Harness
- **The Horse (LLM)**: Bộ não chứa toàn bộ tri thức nhân loại nhưng không biết người dùng, chạy theo xác suất (probabilistic next-token prediction), tiềm ẩn tính ngẫu nhiên (randomness).
- **The Harness (Khung kiểm soát)**: Toàn bộ hệ thống phần mềm bao quanh LLM (Memory, Tools, Loop Control, Guardrails, Evals) để ép "con ngựa" chạy đúng lộ trình và an toàn.

## 2. Tri-Memory Architecture
| Loại trí nhớ                     | Bản chất                             | Lưu trữ                            | Phương thức truy xuất                   | Mục đích                                                       |
| -------------------------------- | ------------------------------------ | ---------------------------------- | --------------------------------------- | -------------------------------------------------------------- |
| **Working Memory / Context RAM** | Tạm thời (Ephemeral)                 | In-context window                  | Trực tiếp                               | Xử lý yêu cầu hiện tại (Prompt + Chat History + System Prompt) |
| **Procedural Memory**            | Quy trình & Kỹ năng                  | Files / Markdown (`SKILL.md`) / DB | Inject vào prompt                       | Hướng dẫn agent cách hành động, công cụ sử dụng                |
| **Semantic Memory**              | Tri thức bền vững (Durable Facts)    | Vector DB / Document Store         | Semantic RAG (Top-K)                    | Lưu facts về user/tổ chức; được chưng cất bởi Summarizer Agent |
| **Episodic Memory**              | Lịch sử sự kiện theo chuỗi thời gian | Time-series DB / SQL + Vector DB   | Hybrid: SQL (recency) + RAG (relevance) | Lưu nhật ký tương tác quá khứ để tham chiếu                    |

## 3. Summarizer Agent & Memory Distillation
- Để tránh tràn database & context window: Thiết lập ngưỡng định kỳ (ví dụ sau mỗi 2000 chats).
- Dùng **Summarizer Agent** chạy model nhỏ, chi phí rẻ để tóm tắt các cuộc hội thoại -> trích xuất facts -> lưu vào Semantic Memory.

## 4. Loop Engineering & End-Loop Guardrails
- **Loop**: Quy trình agent thực hiện chuỗi Tool Calls liên tiếp để hoàn thành mục tiêu phức tạp.
- **End-Loop Guardrails**: Điều kiện dừng bắt buộc nhằm tránh infinite loop / cháy token / hành động ngoài tầm kiểm soát:
  - Task completion condition.
  - Phân nhánh cần người duyệt (Human-in-the-loop / confirmation check).
  - Timeout / Max iterations guardrail.
  - Notification hook (báo người dùng khi cần cấp quyền thay vì treo đợi).

## 5. LLMOps & Continuous Evolution Loop
- **Tracing**: LangFuse / LangSmith ghi lại Trace Tree (User query, Context retrieval, Tool calls, Latency, Token usage).
- **Evaluation**: LLM-as-a-judge + Rule-based assertions đánh giá chất lượng (Success/Fail score, Latency, Token consumption).
- **Diagnosis**: Tìm điểm nghẽn (Tool fail? Memory retrieval quá tải? Prompt mơ hồ?).
- **Feedback & Deploy**: Cập nhật System Prompt / Model Config / RAG params tự động hoặc sửa code -> Rerun -> Tự hoàn thiện theo thời gian.
