### 1. FTPS là gì?

**FTPS** là một phần mở rộng của giao thức FTP (File Transfer Protocol), được thiết kế để khắc phục nhược điểm lớn nhất của FTP truyền thống: **thiếu bảo mật**.

Trong khi FTP thông thường gửi dữ liệu (bao gồm cả tên người dùng và mật khẩu) dưới dạng văn bản thuần (plain text), khiến thông tin dễ dàng bị nghe lén hoặc đánh cắp trên mạng, thì FTPS ra đời để cung cấp một giải pháp an toàn hơn.

### 2. Cơ chế hoạt động của FTPS

Điểm cốt lõi khiến FTPS trở nên an toàn chính là việc bổ sung lớp bảo mật:

- **Sử dụng SSL/TLS:** FTPS sử dụng giao thức **SSL** (Secure Sockets Layer) hoặc **TLS** (Transport Layer Security) để mã hóa toàn bộ quá trình truyền tải dữ liệu giữa máy khách và máy chủ.
    
- **Tạo "đường hầm" an toàn:** Bằng cách áp dụng mã hóa, mọi thông tin nhạy cảm, từ lệnh điều khiển đến nội dung tệp tin, đều được "xáo trộn" thành các ký tự không thể đọc được trước khi gửi đi, đảm bảo tính bảo mật trong quá trình vận chuyển.
    

### 3. Sự khác biệt cần lưu ý (FTPS vs. [[SFTP]])

Trong tài liệu, bạn thường sẽ thấy FTPS và SFTP xuất hiện cùng nhau như các giải pháp thay thế an toàn cho FTP. Tuy nhiên, chúng có cơ chế khác biệt:

- **FTPS (File Transfer Protocol Secure):** Thêm lớp bảo mật bằng SSL hoặc TLS vào giao thức FTP truyền thống.
    
- **SFTP (SSH File Transfer Protocol):** Chạy trên nền tảng giao thức **[[SSH]]** (Secure Shell), một giao thức khác biệt hoàn toàn với FTP về mặt kỹ thuật.
    

### 4. Khi nào nên dùng FTPS?

- **Khi cần truyền tải dữ liệu nhạy cảm:** FTPS được khuyến nghị sử dụng thay cho FTP tiêu chuẩn khi bạn cần gửi các thông tin quan trọng hoặc tệp tin cá nhân.
    
- **Khi muốn giữ cấu trúc FTP:** Nếu hệ thống của bạn đã được thiết lập theo kiến trúc FTP nhưng cần nâng cấp bảo mật mà không muốn thay đổi hoàn toàn sang SSH (SFTP), FTPS là lựa chọn phù hợp.
    

**Tóm lại:** Nếu bạn là một lập trình viên Back-end đang xây dựng hệ thống truyền tải tệp, hãy luôn cân nhắc sử dụng các giao thức có mã hóa như FTPS hoặc SFTP thay vì FTP thuần túy để đảm bảo an toàn tuyệt đối cho dữ liệu của người dùng.