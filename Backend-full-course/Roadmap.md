**1. Nền tảng Mạng máy tính và Giao thức ([[Table]])**
Để lập trình Back-end, bạn cần hiểu cách dữ liệu di chuyển trên Internet:

- **Các mô hình truyền tải cốt lõi ([[Table]]):** Hiểu rõ sự khác biệt giữa giao thức **[[TCP - IP]]** (đảm bảo truyền dữ liệu chính xác, đầy đủ) và **[[UDP]]** (ưu tiên tốc độ, thường dùng cho game, livestream).
- **Hệ thống phân giải:** Tìm hiểu **DNS** (chuyển đổi tên miền thành địa chỉ IP) và **DHCP** (cấp phát địa chỉ IP tự động cho các thiết bị).
- **Giao thức Ứng dụng:** Hiểu cách hoạt động của **HTTP/HTTPS** (giao tiếp web và mã hóa bảo mật) , **FTP/SFTP** (truyền tải file) , email (**SMTP, IMAP, POP3**) , và **SSH** (kết nối và điều khiển server từ xa một cách bảo mật).

**2. Ngôn ngữ lập trình và Hệ sinh thái công nghệ (Programming & Ecosystem)**

- Bắt đầu với một ngôn ngữ mạnh mẽ cho Back-end (ví dụ: JavaScript/Node.js, Python với Django).
- Học cách sử dụng công cụ quản lý mã nguồn như **Git** và **GitHub**.
- Tìm hiểu khái niệm về System Design và các kiến trúc API, ví dụ như **GraphQL**.

**3. Cơ sở dữ liệu và Lưu trữ (Databases)**
Đây là phần cốt lõi của bất kỳ hệ thống Back-end nào:

- **SQL cơ bản:** Sử dụng SQLite, PostgreSQL, hoặc MySQL để thực hiện các truy vấn như tạo, đọc, cập nhật, xóa (CRUD) dữ liệu.
- **Thiết kế Lược đồ (Schema Design) & Chuẩn hóa:** Cách tạo bảng, định nghĩa các kiểu dữ liệu, thiết lập **Khóa chính (Primary Key)** và **Khóa ngoại (Foreign Key)** để mô hình hóa các mối quan hệ 1-1, 1-Nhiều, và Nhiều-Nhiều.
- **Tối ưu hóa Database:** Làm quen với **Index** (chỉ mục) để tăng tốc độ tìm kiếm và sử dụng **Views** để đơn giản hóa hoặc chia nhỏ các bảng dữ liệu phức tạp.
- **Scaling (Mở rộng):** Hiểu các tư duy mở rộng khi lượng dữ liệu lớn như Horizontal Scaling (thêm server/replication) và Sharding (phân mảnh dữ liệu).

**4. Thiết kế, Kiểm thử và Gỡ lỗi API (API Testing & Debugging)**

- **Sử dụng Postman:** Tạo các Request bằng Postman để test API (ví dụ: test phương thức DELETE).
- **Phân tích HTTP Status Code:** Hiểu ý nghĩa các mã lỗi để tìm nguyên nhân. Ví dụ: Lỗi 500 (Sập logic code hoặc database), Lỗi 401/403 (Không có quyền truy cập), Lỗi 404 (Không tìm thấy record).
- **Kỹ năng Debugging (Bắt bệnh):** Học cách đọc log từ terminal của Server. Đây là nơi chứa nguyên nhân gốc rễ, ví dụ như khi xóa record bị cản lại do lỗi ràng buộc khóa ngoại (Foreign Key Constraint) từ database.

**5. Bảo mật, Xác thực và Phân quyền (Authentication & Authorization)** Một lập trình viên Back-end cần phân biệt rõ ràng hai khái niệm này:

- **Xác thực (Authentication):** Xác minh _danh tính_ của người dùng (Who are you?). Các phương pháp bao gồm Basic/Digest Auth, API Keys, Session & Cookies, JWT (JSON Web Tokens).
- **Phân quyền (Authorization):** Xác định những _tài nguyên_ hoặc hành động mà người dùng đó được phép thực hiện (What can you do?).
- **Khung (Frameworks) và Trải nghiệm:** Tìm hiểu về chuẩn phân quyền **OAuth2**, giao thức xác thực **OpenID Connect**, cũng như các khái niệm SSO (Single Sign-On). Bạn cũng nên tìm hiểu thêm về các tiêu chuẩn bảo mật cho API (OWASP API Security).

**6. Mẫu thiết kế phần mềm (Design Patterns)** Để viết code sạch, dễ bảo trì và giải quyết các bài toán lặp đi lặp lại, hãy học 3 nhóm Design Patterns:

- **Creational (Nhóm Khởi tạo):** Quản lý cách tạo object. Nổi bật gồm _Singleton_ (đảm bảo chỉ có 1 bản thể duy nhất như kết nối Database), _Builder_ (xây dựng các object phức tạp từng bước), và _Factory_ (ẩn logic khởi tạo).
- **Structural (Nhóm Cấu trúc):** Cách các object liên kết với nhau, như _Facade_ hay _Adapter_.
- **Behavioral (Nhóm Hành vi):** Xử lý giao tiếp giữa các đối tượng, tiêu biểu như _Strategy_ (thay đổi thuật toán linh hoạt) hay _Observer_ (gửi thông báo event).

**7. DevOps và Môi trường thực tế (Deployment & Tools)**

- Học cách sử dụng **Docker** và **Kubernetes** để ảo hóa và điều phối container.
- Nghiên cứu về các công cụ cache và máy chủ như **Redis**, **NGINX** để tối ưu hóa hiệu năng hệ thống.
