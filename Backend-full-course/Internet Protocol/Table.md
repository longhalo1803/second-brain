**1. Các giao thức truyền tải cốt lõi (Core Transport & Routing)**

- **[[TCP - IP]] (Transmission Control Protocol / Internet Protocol):** Đây là nền tảng của mạng lưới internet hiện đại.
    
    - **TCP:** Đảm bảo truyền tải dữ liệu đáng tin cậy bằng cách chia nhỏ dữ liệu thành các gói (packets) được đánh số, theo dõi, sắp xếp lại theo đúng thứ tự và yêu cầu gửi lại nếu có gói bị mất. Quá trình này bắt đầu bằng một "cái bắt tay 3 bước" (three-way handshake: SYN, SYN-ACK, ACK) để thiết lập kết nối trước khi gửi dữ liệu.
        
    - **IP:** Xử lý việc định địa chỉ và định tuyến để dữ liệu biết cần phải đi đâu. Có hai phiên bản là IPv4 (32-bit) và IPv6 (128-bit) để cung cấp đủ số lượng địa chỉ IP cho mọi thiết bị.
    
- **[[UDP]] (User Datagram Protocol):** Một giao thức truyền tải siêu tốc nhưng không yêu cầu thiết lập kết nối trước (connectionless). UDP không kiểm tra lỗi, không đảm bảo thứ tự gói tin và không gửi lại dữ liệu bị mất. Giao thức này cực kỳ phù hợp cho các ứng dụng cần tốc độ hơn là sự hoàn hảo như livestream, gọi video, hoặc chơi game online.

- **[[QUIC]]:** Một giao thức tốc độ cao do Google phát triển, chạy HTTP trên nền tảng của UDP nhưng lại tích hợp sẵn các lợi ích về bảo mật và độ tin cậy của TCP. Nó gộp quá trình thiết lập kết nối và bảo mật thành một bước duy nhất giúp tải trang và video mượt mà hơn, ngay cả khi mạng chập chờn.

- **[[BGP]] (Border Gateway Protocol):** Giao thức "hoa tiêu" của internet, quyết định cách dữ liệu di chuyển giữa các hệ thống mạng khổng lồ (autonomous systems). BGP trao đổi các thông báo định tuyến để chọn ra con đường khả thi nhất để truyền dữ liệu, tuy nhiên nếu cấu hình sai có thể gây ra sập mạng diện rộng.

**2. Các giao thức Web và Ứng dụng**

- **[[HTTP - HTTPS]] (Hypertext Transfer Protocol / Secure):**  Giao thức nền tảng của web, hoạt động theo mô hình yêu cầu - phản hồi (request - response) giữa trình duyệt và máy chủ để tải các trang web dưới dạng văn bản thuần túy (plain text).
    
    - **HTTPS:** Phiên bản bảo mật của HTTP, bổ sung thêm lớp mã hóa (bằng SSL/TLS) để bảo vệ dữ liệu khỏi bị nghe lén và xác minh danh tính của trang web thông qua các chứng chỉ.
    
- **[[WebSocket]]:** Giao thức cho phép giao tiếp hai chiều liên tục theo thời gian thực trên một kết nối duy nhất, giống như một đường cao tốc riêng không có đèn đỏ. Nó là nền tảng cho các ứng dụng chat trực tiếp, game nhiều người chơi hoặc theo dõi chứng khoán.

**3. Các giao thức Email**

- **SMTP (Simple Mail Transfer Protocol):** Giao thức dùng để gửi (push) và chuyển tiếp email từ thiết bị của bạn đến máy chủ thư điện tử. Nó chỉ lo việc gửi đi, không xử lý việc nhận thư.
    
- **POP3 (Post Office Protocol 3):** Giao thức dùng để nhận thư, nó tải email về thiết bị của bạn và thường xóa luôn bản sao trên máy chủ để bạn đọc ngoại tuyến (offline).
    
- **IMAP (Internet Message Access Protocol):** Cũng dùng để nhận thư nhưng hiện đại hơn, nó lưu email trên máy chủ và đồng bộ hóa trạng thái trên tất cả các thiết bị của bạn.

**4. Các giao thức Truyền tải File**

- **[[FTP]] (File Transfer Protocol):** Dùng để tải lên và tải xuống file giữa máy khách và máy chủ. Nhược điểm là nó gửi dữ liệu dưới dạng văn bản thuần túy nên kém bảo mật.
    
- **[[FTPS]] / [[SFTP]]:** Các phiên bản bảo mật hơn của FTP. FTPS thêm mã hóa SSL/TLS, trong khi SFTP chạy trên nền giao thức SSH để truyền file an toàn.

**5. Các giao thức Quản lý mạng và Hệ thống**

- **[[DNS]] (Domain Name System):** Đóng vai trò như danh bạ điện thoại của internet, dịch các tên miền dễ nhớ (như google.com) thành địa chỉ IP để máy tính có thể giao tiếp với nhau.
    
- **[[DHCP]] (Dynamic Host Configuration Protocol):** Tự động cấp phát địa chỉ IP và các cấu hình mạng khác (subnet mask, default gateway, DNS server) cho thiết bị khi kết nối vào mạng, giúp tránh xung đột IP. Quá trình này trải qua 4 bước gọi là DORA (Discover, Offer, Request, Acknowledge).
    
- **[[ARP]] (Address Resolution Protocol):** Giao thức dùng để ánh xạ một địa chỉ IP sang địa chỉ vật lý MAC bên trong một mạng nội bộ (local network) bằng cách gửi các yêu cầu phát sóng (broadcast request).
    
- **[[ICMP]] (Internet Control Message Protocol):** Giao thức chẩn đoán mạng, gửi các thông báo lỗi và thông tin hoạt động. Các công cụ như Ping hoặc Trace Route dùng ICMP để kiểm tra xem thiết bị đích có thể kết nối được không.
    
- **[[SNMP]] (Simple Network Management Protocol):** Quản lý và giám sát các thiết bị mạng (router, server, switch) từ một hệ thống trung tâm.
    
- **[[NTP]] (Network Time Protocol):** Đồng bộ hóa đồng hồ của tất cả các máy tính và thiết bị trong mạng dựa trên các nguồn thời gian chính xác (như đồng hồ nguyên tử) để đảm bảo không có sai lệch trong hệ thống.
    
- **[[RIP & OSPF]]:** Là các giao thức định tuyến. RIP đếm số bước nhảy (hop) để tìm đường nhưng bị giới hạn tốc độ và quy mô. OSPF tiến tiến hơn, tính toán chi phí con đường (cost-based) để tìm ra đường truyền nhanh và mở rộng tốt hơn.

**6. Các giao thức Bảo mật và Truy cập từ xa**

- **[[SSH]] (Secure Shell):** Cho phép truy cập và điều khiển máy chủ từ xa một cách bảo mật. SSH mã hóa mọi dữ liệu và sử dụng các phương thức xác thực mạnh (như cặp khóa mật mã public/private key).
    
- **Telnet:** Giao thức quản lý từ xa qua dòng lệnh đời cũ. Vì gửi mọi dữ liệu (kể cả mật khẩu) dưới dạng văn bản không mã hóa nên nó được coi là lỗi thời và nguy hiểm.
    
- **[[TLS]] / [[SSL]] (Transport Layer Security / Secure Sockets Layer):** Lớp bảo vệ vô hình mã hóa dữ liệu giữa thiết bị và máy chủ. SSL đã cũ và hiện nay TLS 1.3 là chuẩn bảo mật hiện đại được áp dụng.