# Learning Record 0003: Model Context Protocol (MCP) Deep Dive & Custom Server Implementation

- **Date**: 2026-08-26
- **Topic**: Giao thức chuẩn hóa Model Context Protocol (MCP) & Xây dựng MCP Server cá nhân
- **Sources Analyzed**:
  - Anthropic Official Documentation (`modelcontextprotocol.io`)
  - Video 1: *Understanding Model Context Protocol* (cGuyrANVi4A)
  - Video 2: *MCP vs Traditional APIs & The Future of AI Integration* (185XGEMefgc)

## 1. Key Architectural Insights
1. **Tại sao API truyền thống không đủ cho LLM?**
   - API truyền thống thiết kế cho chương trình xác định (Deterministic code), đòi hỏi phải biết trước endpoint và cấu trúc cứng.
   - LLM hoạt động theo cơ chế xác suất (Probabilistic) và tự suy luận $\to$ Cần một **Giao thức ngữ nghĩa (Semantic Protocol)** có khả năng **Tự quảng bá (Auto-discovery)** danh sách công cụ và tài nguyên.
2. **MCP là tầng Middleware nằm trên API**:
   - MCP không thay thế API, mà bọc các API lại thành định dạng thân thiện với Model.
   - Client của MCP chính là **Mô hình AI**, không phải người lập trình.
3. **3 Khối năng lực của MCP (Primitives)**:
   - **Tools**: Hành động có thể thực thi (`@mcp.tool()`).
   - **Resources**: Dữ liệu chỉ đọc được định danh bằng URI (`@mcp.resource()`).
   - **Prompts**: Mẫu hướng dẫn có thể tái sử dụng (`@mcp.prompt()`).
4. **Cơ chế truyền tải (Transports)**:
   - `stdio`: Cho các tiến trình local (nhanh, an toàn, chuẩn mặc định cho desktop agents).
   - `sse` (Server-Sent Events qua HTTP): Cho các server từ xa.

## 2. Cách Tạo MCP Server Cá Nhân
- Dùng `FastMCP` trong thư viện `mcp` của Python.
- Kiểm thử bằng **MCP Inspector** (`npx @modelcontextprotocol/inspector python3 <file.py>`).
- Cấu hình vào Client (Claude Desktop / Cursor / Antigravity) qua file JSON config.

## 3. Liên Kết Kiến Thức
- Liên kết với [[04 - Agent Architecture & Loop Engineering/04.2 - Loop Engineering & Tool Calling|04.2 - Loop Engineering]]: MCP chuẩn hóa cơ chế Tool Calling không cần viết lại glue code.
- Liên kết với [[05 - Frameworks & Tooling/05.1 - LangChain & LangGraph Deep Dive|05.1 - LangGraph]]: LangGraph có thể làm MCP Client để kết nối các MCP Server bên ngoài.
