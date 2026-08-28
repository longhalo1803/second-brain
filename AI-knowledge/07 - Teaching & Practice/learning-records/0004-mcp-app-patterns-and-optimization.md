# Learning Record 0004: MCP Architecture Patterns Across Apps & Performance Optimization

- **Date**: 2026-08-26
- **Topic**: Phân loại các mẫu thiết kế MCP cho từng loại ứng dụng & Kỹ thuật tối ưu hóa hiệu năng
- **Status**: Completed

## 1. Bản Chất Đồng Nhất & Khác Biệt Giữa Các MCP Server
- **Điểm đồng nhất (The Protocol Standard)**: Mọi MCP Server đều tuân theo cùng 1 chuẩn giao tiếp JSON-RPC 2.0 (Tools, Resources, Prompts) và cấu hình giống hệt nhau trên các Client (Claude, Cursor, Antigravity).
- **Điểm khác biệt (The Under-the-hood Execution)**: Tùy loại ứng dụng đích mà logic bên trong hàm tool sẽ khác nhau:
  1. *Local / OS Tools (Git, File, Shell)*: Gọi Subprocess hoặc File I/O trực tiếp.
  2. *Cloud SaaS (GitHub, Slack, Jira, Notion)*: Gọi REST / GraphQL API kèm Bearer Token / OAuth.
  3. *Databases (PostgreSQL, Redis, Vector DB)*: Dùng DB Driver qua kết nối TCP wire socket.
  4. *Browser / GUI Apps (Chrome, Blender)*: Dùng CDP (Chrome DevTools Protocol) hoặc WebSocket RPC.

## 2. 5 Trụ Cột Tối Ưu Hóa MCP Server
1. **Token Budget & Context Optimization**:
   - Viết Tool Description ngắn gọn, súc tích (1-2 câu).
   - Cắt ngắn (Truncate) và Phân trang (Pagination) output của Tool; không bao giờ trả về toàn bộ 100MB log.
   - Hỗ trợ Lazy Loading / Eager Loading cho các tool ít dùng.
2. **Độ trễ & Thông lượng (Latency & Throughput)**:
   - Sử dụng Async I/O (`asyncio`, `httpx.AsyncClient`, `asyncpg`).
   - Duy trì Connection Pooling thay vì tạo kết nối HTTP/DB mới ở mỗi lượt gọi.
   - Caching in-memory (TTL cache) cho các dữ liệu ít thay đổi.
3. **Khả năng tự phục hồi của Model (Model Recovery & Self-Correction)**:
   - Trả về thông báo lỗi có định hướng (Actionable Error Message) thay vì quăng raw exception.
   - Dùng Pydantic validation cho tham số đầu vào.
4. **An toàn & Kiểm soát rủi ro (Security & Guardrails)**:
   - Tách biệt rõ Tool Đọc (Read-only) và Tool Ghi/Phá hủy (Mutations).
   - Hỗ trợ cờ `dry_run=True` để AI mô phỏng kết quả trước khi thực thi thật.
