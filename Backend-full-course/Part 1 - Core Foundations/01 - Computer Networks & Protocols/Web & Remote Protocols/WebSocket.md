---
title: Giao Thức WebSocket
aliases:
  - WebSocket Protocol
  - WSS
  - RFC 6455
tags:
  - backend
  - networks
  - realtime
  - websocket
type: concept
status: completed
created: 2026-09-25
updated: 2026-09-25
---

# ⚡ Giao Thức WebSocket (Full-Duplex Realtime Communication)

> [[00 - Networks MOC|📁 Computer Networks MOC]] / [[MOC - Part 1 Core Foundations|🟢 Part 1 MOC]]

---

## 1. Bản Đồ Khái Niệm (Mermaid DAG)

```mermaid
sequenceDiagram
    autonumber
    actor Client
    actor Server

    Note over Client,Server: Pha 1: Bắt Tay Nâng Cấp Giao Thức (HTTP Upgrade)
    Client->>Server: GET /chat HTTP/1.1 (Upgrade: websocket, Sec-WebSocket-Key: ...)
    Server->>Client: HTTP/1.1 101 Switching Protocols (Sec-WebSocket-Accept: ...)

    Note over Client,Server: Pha 2: Kênh Truyền Song Công Toàn Phần (Bi-directional Frames)
    Client->>Server: WebSocket Binary/Text Frame (Masked)
    Server->>Client: WebSocket Binary/Text Frame (Unmasked)
    Server-->>Client: Push Data (Server chủ động đẩy dữ liệu bất kỳ lúc nào)

    Note over Client,Server: Pha 3: Duy Trì & Đóng Kết Nối
    Client->>Server: Ping Frame
    Server->>Client: Pong Frame
    Client->>Server: Close Frame
    Server->>Client: Close Frame
```

---

## 2. Chân Lý Vô Điều Kiện (First Principles)

> [!NOTE] Tiên Đề Bất Biến
> **WebSocket là giao thức song công toàn phần (Full-duplex), hướng thông điệp (Message-oriented) chạy trên một kết nối TCP duy nhất.**
>
> Sau pha nâng cấp giao thức ban đầu (HTTP Upgrade), kết nối TCP được giải phóng hoàn toàn khỏi các quy tắc của HTTP. Client và Server có thể độc lập gửi và nhận dữ liệu bất kỳ lúc nào mà không cần gửi kèm HTTP Headers, giảm overhead mỗi gói tin xuống chỉ còn **2 đến 10 bytes**.

---

## 3. Trực Giác Motivated Discovery

> [!TIP] Động Lực Phát Minh (Tại sao không dùng HTTP Polling?)
>
> - **Short Polling:** Client cứ 2 giây gửi 1 HTTP GET để hỏi "Có tin nhắn mới không?". 99% câu trả lời là "Không có". Mỗi request tốn ~1 KB HTTP header $
>   ightarrow$ Băng thông lãng phí khổng lồ, server quá tải connection.
> - **Long Polling:** Server giữ request treo (pending) cho đến khi có tin mới. Dù tốt hơn nhưng mỗi lần trả lời xong lại phải thiết lập lại kết nối HTTP mới.
> - **WebSocket:** Mở duy nhất một đường ống hai chiều vĩnh cửu. Server có tin là đẩy ngay tức thì với độ trễ tính bằng mili-giây, cực kỳ tối ưu cho ứng dụng Chat, Gaming, Bảng giá tài chính.

---

## 4. Phân Tích Kỹ Thuật Chuyên Sâu

### 4.1. Cơ Chế Bắt Tay Nâng Cấp (Handshake)

1. Client gửi HTTP GET Request với các headers đặc biệt:
   ```http
   GET /socket.io/ HTTP/1.1
   Host: example.com
   Upgrade: websocket
   Connection: Upgrade
   Sec-WebSocket-Key: dGhlIHNhbXBsZSBub25jZQ==
   Sec-WebSocket-Version: 13
   ```
2. Server tính toán `Sec-WebSocket-Accept`:
   - Nối chuỗi `Sec-WebSocket-Key` với một GUID chuẩn hóa bí mật (`258EAFA5-E914-47DA-95CA-C5AB0DC85B11`).
   - Băm SHA-1 chuỗi trên rồi mã hóa Base64.
   - Trả lời `101 Switching Protocols`.

---

### 4.2. Cấu Trúc Khung Tin (WebSocket Frame)

Khác với HTTP gửi văn bản, WebSocket truyền tải dạng khung nhị phân:

- `FIN (1 bit)`: Đánh dấu frame cuối cùng của message.
- `Opcode (4 bits)`: Loại frame (`0x1`: Text, `0x2`: Binary, `0x8`: Close, `0x9`: Ping, `0xA`: Pong).
- `MASK (1 bit)`: Bắt buộc bằng 1 nếu frame gửi từ Client (ngăn chặn tấn công Cache Poisoning ở các proxy trung gian).
- `Payload Length (7, 7+16, hoặc 7+64 bits)`: Độ dài dữ liệu.

---

### 4.3. So Sánh Kiến Trúc Thời Gian Thực

| Tiêu Chí              | HTTP Polling                        | Server-Sent Events (SSE)         | WebSocket                        |
| :-------------------- | :---------------------------------- | :------------------------------- | :------------------------------- |
| **Chiều truyền**      | 2 chiều (bị động)                   | 1 chiều (Server $                |
| ightarrow$ Client)    | **2 chiều toàn phần (Full-duplex)** |
| **Giao thức**         | HTTP                                | HTTP                             | WebSocket (sau khi Upgrade)      |
| **Overhead**          | Rất cao (~1 KB/req)                 | Thấp                             | **Siêu thấp (2-10 bytes/frame)** |
| **Hỗ trợ nhị phân**   | Có                                  | Không (chỉ UTF-8 text)           | **Có (ArrayBuffer, Blob)**       |
| **Use Case tốt nhất** | Dashboard ít update                 | Notification, AI Streaming (LLM) | **Chat, Game, Sàn chứng khoán**  |

---

## 5. Spaced Repetition Flashcards & Tham Chiếu

### Flashcards

Mục đích của việc mã hóa Masking Key trong các frame WebSocket từ Client gửi lên Server là gì? #card
Ngăn ngừa tấn công Cache Poisoning trên các Proxy/Router trung gian. Masking làm cho nội dung khung tin có tính ngẫu nhiên, khiến các thiết bị trung gian không nhầm lẫn frame WebSocket với các lệnh HTTP hợp lệ.

Mã phản hồi HTTP nào được Server trả về khi chấp nhận nâng cấp kết nối lên WebSocket? #card
HTTP Status Code 101 Switching Protocols.

Khi nào nên chọn Server-Sent Events (SSE) thay vì WebSocket trong ứng dụng Backend? #card
Khi chỉ cần truyền dữ liệu một chiều từ Server về Client (như streaming câu trả lời từ AI LLM, cập nhật thông báo, tiến độ xử lý file), giúp tận dụng giao thức HTTP/2 hiện có mà không cần quản lý kết nối socket hai chiều phức tạp.

### Tham Chiếu

- [[HTTP - HTTPS]] - Giao thức khởi tạo nền tảng cho quá trình bắt tay WebSocket.
- [[TCP - IP]] - Giao thức truyền vận đảm bảo phân phát dữ liệu tin cậy cho WebSocket.
- [[TLS]] - Cung cấp mã hóa WSS (WebSocket Secure) qua cổng 443.
