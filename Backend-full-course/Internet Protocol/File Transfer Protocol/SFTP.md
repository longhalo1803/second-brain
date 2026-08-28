### 1. SFTP là gì?

SFTP (SSH File Transfer Protocol) là giao thức truyền tải tệp tin an toàn hoạt động dựa trên nền tảng của giao thức **[[SSH]] (Secure Shell)**.

Thay vì sử dụng giao thức FTP cũ làm nền tảng, SFTP tận dụng sức mạnh của SSH — vốn là "con dao đa năng" mà quản trị viên dùng để truy cập, điều khiển và quản lý server từ xa.

### 2. Tại sao SFTP được coi là tiêu chuẩn an toàn?

Khác với FTP thuần (gửi dữ liệu dưới dạng văn bản thuần, dễ bị nghe lén), SFTP bảo mật hơn nhờ các yếu tố sau:

- **Mã hóa hoàn toàn:** Vì chạy trên nền SSH, SFTP mã hóa mọi dữ liệu được truyền đi, bao gồm cả tên đăng nhập, mật khẩu và nội dung tệp tin.
    
- **Xác thực mạnh:** SFTP hỗ trợ các phương thức xác thực mạnh của SSH, như sử dụng cặp khóa mật mã (public/private key) thay vì chỉ dùng mật khẩu thông thường, giúp ngăn chặn hiệu quả các cuộc tấn công.
    
- **Kênh duy nhất:** Không giống như FTP cần hai kết nối riêng biệt (một cho điều khiển, một cho dữ liệu) gây rắc rối với tường lửa, SFTP chỉ sử dụng một kết nối duy nhất, giúp nó dễ dàng vượt qua các bức tường lửa hơn.
    

### 3. Phân biệt [[FTPS]] và SFTP (Điểm dễ gây nhầm lẫn)

Mặc dù mục đích cuối cùng đều là truyền file an toàn, nhưng cách thực hiện rất khác nhau:

|**Đặc điểm**|**FTPS**|**SFTP**|
|---|---|---|
|**Nền tảng**|Dựa trên FTP + SSL/TLS|Dựa trên SSH|
|**Độ phức tạp**|Khá phức tạp với tường lửa do dùng nhiều cổng|Rất đơn giản, chỉ dùng 1 cổng (thường là 22)|
|**Phổ biến**|Ít hơn trong môi trường Dev/Ops|**Chuẩn mực** trong quản trị server|

### 4. Lời khuyên cho Lập trình viên Back-end

Trong lộ trình trở thành Back-end developer, bạn sẽ làm việc với SFTP hàng ngày:

- **Deployment:** Khi bạn cần đẩy code từ máy cá nhân lên Server (Deploy), SFTP là giao thức chính để truyền file.
    
- **Quản trị:** Khi bạn cần truy cập vào server để sửa file cấu hình hoặc lấy log từ xa, bạn sẽ dùng SSH. Vì SFTP dùng chung giao thức với SSH, bạn sẽ thấy nó cực kỳ tiện lợi và đồng bộ.
    

**Tóm lại:** Nếu bạn có quyền chọn lựa giữa FTP, FTPS và SFTP, thì **SFTP luôn là lựa chọn hàng đầu** nhờ tính bảo mật cao, sự ổn định và dễ cấu hình qua tường lửa.