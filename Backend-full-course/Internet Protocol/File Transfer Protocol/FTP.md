**FTP** là một giao thức mạng tiêu chuẩn được sử dụng để chuyển tải các tệp tin giữa một máy khách (client) và một máy chủ (server) qua mạng internet hoặc mạng nội bộ.

- **Mô hình hoạt động:** FTP vận hành theo mô hình **Client-Server**. Máy khách kết nối đến server để thực hiện các thao tác: tải lên (upload), tải xuống (download), đổi tên, xóa hoặc quản lý tệp tin trên máy chủ.
    
- **Quyền truy cập:** FTP hỗ trợ cả hai phương thức: truy cập ẩn danh (anonymous) không cần thông tin xác thực và truy cập yêu cầu tài khoản (username/password).
    

### 2. Kiến trúc đặc biệt của FTP

Điểm khác biệt lớn nhất của FTP so với các giao thức khác (như HTTP) là nó sử dụng **hai kết nối riêng biệt** để hoàn thành công việc:

1. **Control Connection (Kết nối điều khiển):** Dùng để gửi các lệnh quản lý như đăng nhập, thay đổi thư mục, yêu cầu liệt kê file.
    
2. **Data Connection (Kết nối dữ liệu):** Thực sự chuyển tải nội dung của tệp tin.
    

### 3. Chế độ kết nối: Active vs. Passive

Khi làm việc với các hệ thống có tường lửa (firewall), bạn cần hiểu cơ chế này:

- **Active Mode:** Server chủ động kết nối lại máy khách để truyền dữ liệu.
    
- **Passive Mode:** Máy khách chủ động kiểm soát cả hai kết nối. Đây là chế độ phổ biến hơn hiện nay vì nó hoạt động tốt hơn qua các bức tường lửa (vốn thường chặn các kết nối lạ từ server đi vào máy client).
    

### 4. Cảnh báo bảo mật: Tại sao không nên dùng FTP thuần?

Đây là kiến thức quan trọng nhất mà bạn cần ghi nhớ khi làm Back-end:

> FTP truyền tải mọi thông tin dưới dạng văn bản thuần (plain text), bao gồm cả tên người dùng và mật khẩu.

Điều này có nghĩa là bất kỳ ai có khả năng chặn bắt gói tin (eavesdropping) trên mạng đều có thể dễ dàng đọc được thông tin đăng nhập của bạn. Vì lý do bảo mật, FTP thuần hiện nay được coi là lỗi thời đối với việc truyền tải dữ liệu nhạy cảm.

### 5. Các giải pháp thay thế an toàn

Thay vì FTP, trong các dự án chuyên nghiệp, chúng ta luôn ưu tiên sử dụng:

- **[[FTPS]]:** Là phiên bản FTP được bổ sung thêm lớp mã hóa **SSL/TLS** để bảo mật dữ liệu.
    
- **[[SFTP]]:** (SSH File Transfer Protocol) Chạy trên nền tảng của giao thức **[[SSH]]**. Đây là phương pháp cực kỳ an toàn vì nó tận dụng khả năng mã hóa và xác thực mạnh mẽ của SSH.
    

### 6. Ứng dụng thực tế

Dù có vấn đề về bảo mật, FTP vẫn tồn tại và được sử dụng rộng rãi nhờ tính đơn giản và sự hỗ trợ mạnh mẽ trên mọi hệ thống. Bạn sẽ thường gặp nó trong các trường hợp:

- Quản lý tệp tin trên các server cũ hoặc hệ thống website đơn giản.
    
- Truyền tải các tập dữ liệu lớn không yêu cầu mức độ bảo mật khắt khe.
    

**Tư duy Back-end:** Nếu bạn đang xây dựng một hệ thống cần truyền tải file, hãy luôn ưu tiên **SFTP** để đảm bảo an toàn. Nếu hệ thống của bạn bắt buộc phải dùng FTP, hãy đảm bảo nó được nằm trong một mạng nội bộ (private network) an toàn và không bị công khai trên Internet.