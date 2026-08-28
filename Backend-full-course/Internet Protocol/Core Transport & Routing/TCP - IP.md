# TCP/IP Model in computer network - Mô hình TCP/IP trong mạng máy tính

# I. Mô hình TCP/IP

Mô hình **TCP/IP** (**Transmission Control Protocol/Internet Protocol**) là một bộ giao thức mạng được thiết kế để kết nối mạng máy tính với nhau. Không chỉ là một bộ giao thức duy nhất, **TCP/IP** là một hệ thống các giao thức liên kết với nhau, cung cấp khả năng truyền tải dữ liệu từ máy này sang máy khác thông qua mạng.

Ban đầu, **TCP/IP** được thiết kế để đảm bảo sự trao đổi thông tin an toàn, đáng tin cậy và hiệu quả giữa các máy tính, ngay cả trong điều kiện mạng không ổn định. Với sự kết hợp của **TCP** - quản lý dữ liệu trong dạng luồng tin cậy, và **IP** - xác định địa chỉ và định tuyến dữ liệu trong mạng, **TCP/IP** đã trở thành tiêu chuẩn không thể thiếu trong việc thiết lập và duy trì mạng máy tính từ quy mô nhỏ đến quy mô lớn trên toàn thế giới. Điểm nổi bật của nó nằm ở khả năng tương tác giữa các loại máy tính khác nhau và sự độc lập với kiến trúc phần cứng, cho phép nó trở thành một tiêu chuẩn mạng toàn cầu.

**TCP/IP** thực chất là một bộ giao thức (suite) bao gồm hai thành phần chính, mỗi thành phần đảm nhiệm một nhiệm vụ riêng biệt:

- **TCP (Transmission Control Protocol - Giao thức điều khiển truyền tải):** Đóng vai trò là "người hướng dẫn giao hàng" đảm bảo độ tin cậy.
    
    - **Cái bắt tay 3 bước (Three-way Handshake):** Trước khi truyền dữ liệu, **TCP** thiết lập kết nối giữa người gửi và người nhận thông qua quá trình: Thiết bị gửi (**SYN**) -> Thiết bị nhận (**SYN-ACK**) -> Thiết bị gửi xác nhận (**ACK**).
        
    - **Phân đoạn và Sắp xếp:** Dữ liệu lớn được chia thành các gói (**packets**) nhỏ, được đánh số thứ tự để **TCP** có thể sắp xếp lại đúng trình tự tại đích đến.
        
    - **Đảm bảo truyền tải:** Nếu một gói tin bị mất hoặc hỏng trên đường đi, **TCP** sẽ yêu cầu gửi lại gói đó, đảm bảo dữ liệu đến đích đầy đủ và chính xác.
    
- **IP (Internet Protocol - Giao thức Internet):** Đóng vai trò là "hệ thống địa chỉ".
    
    - **Định địa chỉ:** Mỗi thiết bị trên Internet được cấp một địa chỉ **IP** (như địa chỉ nhà) để xác định vị trí trong mạng lưới.
        
    - **Định tuyến (Routing):** **IP** quyết định con đường mà các gói tin sẽ đi để đến đúng địa chỉ đích.
        
    - **Phiên bản:** Có hai loại chính: **IPv4** (32-bit, cung cấp khoảng 4,3 tỷ địa chỉ) và **IPv6** (128-bit, cung cấp số lượng địa chỉ khổng lồ để đáp ứng nhu cầu toàn cầu).

![[Pasted image 20260617104439.png]]

Hiện nay, mô hình **TCP/IP** được coi là bộ xương sống của Internet và là một trong những công nghệ cơ bản nhất giúp xây dựng mạng máy tính hiện đại, bao gồm 4 tầng:

- Tầng ứng dụng (**Application Layer**)
- Tầng giao vận (**Transport Layer**)
- Tầng mạng (**Network Layer**)
- Tầng truy cập mạng (**Network Access Layer**)
![[Pasted image 20260617103429.png]]

## So sánh mô hình TCP/IP và OSI

Trong thế giới mạng máy tính, hai mô hình nổi bật và quan trọng nhất là mô hình **OSI** (**Open Systems Interconnection**) và mô hình **TCP/IP** (**Transmission Control Protocol/Internet Protocol**). Mỗi mô hình đều cung cấp một khung tham chiếu giúp hiểu biết và thiết kế các hệ thống mạng máy tính, nhưng chúng có những đặc điểm và cách tiếp cận khác nhau.

Bên cạnh **OSI** model được xem là mô hình lý thuyết hơn và có nhiều tầng chi tiết, mô hình **TCP/IP** được coi là phiên bản rút gọn của **OSI**, được áp dụng rộng rãi trong thực tế. Mô hình **TCP/IP** tập trung vào ứng dụng thực tế, các tầng được đánh giá là linh hoạt hơn, dễ dàng điều chỉnh để phù hợp với các yêu cầu cụ thể và mở rộng.

![[Pasted image 20260617103456.png]]

# II. Các tầng trong mô hình TCP/IP

Mô hình TCP/IP được tổ chức thành bốn tầng, mỗi tầng đảm nhận một nhóm các nhiệm vụ cụ thể và làm việc với các tầng khác để truyền dữ liệu từ nguồn đến đích một cách hiệu quả. Chúng ta sẽ lần lượt đi qua mô tả chi tiết về mỗi tầng trong mô hình để có cái nhìn sâu hơn về mô hình.

## 1. Tầng truy cập mạng (Network Access Layer)

Tương ứng với hai tầng vật lý và liên kết dữ liệu trong mô hình OSI, tầng truy cập mạng trong mô hình TCP/IP đảm bảo việc gửi và nhận dữ liệu trên phương tiện vật lý của mạng. Tầng này xử lý tất cả vấn đề liên quan đến cách dữ liệu được truyền từ thiết bị này sang thiết bị khác. Bao gồm việc đóng gói dữ liệu thành khung (frame), xác định địa chỉ vật lý, và kiểm soát quyền truy cập vào môi trường truyền dẫn.

## 2. Tầng mạng (Network/internet Layer)

Tầng mạng có trách nhiệm chính trong việc định tuyến các gói tin từ nguồn đến đích. Tầng này sử dụng giao thức IP để xác định địa chỉ duy nhất cho mỗi thiết bị và quyết định đường đi của dữ liệu trong mạng. Tầng mạng đảm nhận việc phân mảnh và tái tổ hợp các gói tin, xử lý lỗi, và cập nhật các thông tin định tuyến.

## 3. Tầng giao vận (Transport Layer)

Tầng giao vận chịu trách nhiệm cho việc truyền dữ liệu đáng tin cậy giữa các ứng dụng chạy trên các thiết bị khác nhau. Nó đảm bảo dữ liệu được truyền một cách chính xác, không bị lỗi, và theo thứ tự đúng.

Tầng giao vận thực hiện việc kiểm soát lỗi, kiểm soát luồng dữ liệu, và cung cấp các cơ chế truyền thông đặc biệt như truyền thông đáng tin cậy (TCP) và truyền thông không đáng tin cậy nhưng nhanh chóng (UDP).

## 4. Tầng ứng dụng (Application Layer)

Có thể coi là sự kết hợp của ba tầng phiên, tầng trình diễn, tầng ứng dụng trong mô hình OSI, tầng ứng dụng trong mô hình TCP/IP cung cấp các dịch vụ mạng cần thiết cho các ứng dụng mà người dùng sử dụng, như trình duyệt web, email, và các dịch vụ truyền file.

Tầng ứng dụng cung cấp các giao thức ứng dụng như HTTP, SMTP, FTP, ..., đảm bảo người dùng có thể tương tác với mạng một cách suôn sẻ và hiệu quả.

# III. Ví dụ minh họa về hoạt động giữa các tầng trong mô hình TCP/IP

## 1. Gửi email

Khi bạn gửi email, ứng dụng email sử dụng SMTP (tầng ứng dụng) để gửi thông điệp. Thông điệp được chuyển xuống tầng giao vận, ở đây thực hiện phân chia thông điệp thành các gói và gửi chúng. Sau đó tầng mạng sử dụng giao thức IP để định tuyến các gói này qua mạng. Cuối cùng, tầng truy cập mạng sẽ gửi dữ liệu qua các phương tiện vật lý.

## 2. Truy cập trang web

Khi bạn truy cập một trang web sẽ tạo ra yêu cầu (request), trình duyệt sử dụng HTTP/HTTPs (tầng ứng dụng) để yêu cầu trang từ máy chủ. Yêu cầu được chuyển xuống tầng giao vận, nơi TCP phân chia dữ liệu thành gói, định tuyến gói qua tầng mạng, và tầng truy cập mạng gửi gói qua mạng.

## 3. Chia sẻ tệp qua FTP

Khi bạn tải tệp lên hoặc tải xuống từ máy chủ FTP, ứng dụng FTP (tầng ứng dụng) đóng vai trò bắt đầu quá trình. Dữ liệu được chia thành gói trong tầng giao vận, định tuyến qua mạng (tầng mạng), và cuối cùng được truyền đi (tầng truy cập mạng).

# IV. Tầm quan trọng của mô hình TCP/IP

## 1. Chuẩn hóa truyền thông mạng

- Độc lập với thiết bị: TCP/IP cung cấp một phương thức truyền thông độc lập với phần cứng, cho phép các thiết bị từ nhiều nhà sản xuất khác nhau có thể giao tiếp với nhau mà không cần bất kỳ phần cứng trung gian/liên kết nào.
    
- Tương thích trên quy mô toàn cầu: Mô hình TCP/IP đảm bảo rằng các mạng khác nhau có thể tương tác và hợp nhất một cách suôn sẻ, từ đó hình thành nên một mạng lưới toàn cầu.
    

## 2. Độ tin cậy và kiểm soát lỗi

- Truyền dữ liệu tin cậy: TCP/IP có cơ chế kiểm soát lỗi mạnh mẽ, đảm bảo rằng dữ liệu được truyền một cách chính xác, không bị mất mát hoặc hỏng hóc trong quá trình truyền.
    
- Quản lý luồng và kiểm soát tắc nghẽn: TCP, một phần của mô hình TCP/IP, giúp quản lý luồng dữ liệu và ngăn chặn tắc nghẽn mạng, đảm bảo hiệu suất mạng ổn định.
    

## 3. Tính mở rộng và linh hoạt

- Mở rộng dễ dàng: Mô hình TCP/IP cho phép mạng mở rộng mà không làm ảnh hưởng đến hiệu suất hoạt động hiện tại của mạng.
    
- Hỗ trợ đa dạng các mạng: TCP/IP có thể được sử dụng trong nhiều loại mạng khác nhau, từ mạng LAN (Local Area Network) nhỏ đến mạng WAN (Wide Area Network) rộng lớn như Internet.
    

## 4. Đóng góp cho sự phát triển của Internet

- Phát triển dịch vụ Internet: Mô hình TCP/IP là cơ sở cho việc phát triển các ứng dụng internet như trình duyệt web, email, truyền file, và nhiều dịch vụ khác.
    
- Hỗ trợ công nghệ Mới: TCP/IP cung cấp cơ sở vững chắc cho sự phát triển của các công nghệ và ứng dụng mới trên Internet, như IoT (Internet of Things), cloud computing, và nhiều hơn nữa.
    

## 5. An ninh và quản lý mạng

- Quản lý mạng hiệu quả: TCP/IP cung cấp các công cụ và giao thức để quản lý mạng một cách hiệu quả, giúp phát hiện và giải quyết các vấn đề mạng.
    
- Tăng cường an ninh mạng: Mặc dù TCP/IP không phải là giải pháp an ninh toàn diện, nó hỗ trợ và làm việc chặt chẽ với các giao thức an ninh như SSL/TLS trong việc bảo vệ dữ liệu và thông tin truyền trên mạng.
    


# V. Áp dụng thực tế trong lập trình Back-end

Khi bạn lập trình Back-end, TCP/IP hoạt động "ẩn mình" bên dưới các giao thức ứng dụng mà bạn trực tiếp sử dụng hàng ngày:

- **HTTP/HTTPS:** Khi bạn viết API (dùng `GET`, `POST`, `DELETE`...), thực chất bạn đang truyền dữ liệu trên nền tảng của TCP. HTTP/HTTPS sử dụng sự tin cậy của TCP để đảm bảo yêu cầu (request) của người dùng đến server và phản hồi (response) trả về không bị mất mát.
    
- **Truyền tải file (FTP/SFTP):** Khi ứng dụng của bạn cần upload/download dữ liệu lớn, giao thức FTP/SFTP tận dụng TCP để đảm bảo file sau khi truyền tải không bị lỗi (corrupted).
    
- **Quản trị từ xa ([[SSH]]):** Khi bạn dùng SSH để đăng nhập vào máy chủ (server), TCP tạo kết nối ổn định để các lệnh bạn gõ từ terminal truyền chính xác đến máy chủ mà không bị nhiễu loạn.
    

### 3. Tư duy so sánh: TCP vs [[UDP]]

Để lập trình Back-end hiệu quả, bạn cần biết khi nào nên dùng TCP (đáng tin cậy) và khi nào dùng UDP (tốc độ cao):

|**Đặc điểm**|**TCP (Transmission Control Protocol)**|**UDP (User Datagram Protocol)**|
|---|---|---|
|**Độ tin cậy**|Cao, đảm bảo dữ liệu đến đích.|Thấp, không đảm bảo dữ liệu đến đích.|
|**Kết nối**|Phải thiết lập kết nối (handshake).|Không kết nối (connectionless).|
|**Tốc độ**|Chậm hơn do overhead xử lý.|Rất nhanh.|
|**Ứng dụng**|Web (HTTP), Email, Chuyển file.|Live streaming, Game online, Voip.|

**Tóm lại:** TCP/IP là "xương sống" của hạ tầng mạng. Là một lập trình viên Back-end, bạn không cần phải viết code tạo kết nối TCP từ đầu, nhưng hiểu cách nó vận hành (như lỗi mất gói tin, độ trễ do handshaking) sẽ giúp bạn **debug các vấn đề về kết nối mạng** giữa client và server hoặc tối ưu hiệu năng cho hệ thống của mình.

# Tài liệu tham khảo

- [https://www.geeksforgeeks.org/tcp-ip-model/](https://www.geeksforgeeks.org/tcp-ip-model/)
- [https://www.geeksforgeeks.org/tcp-ip-in-computer-networking/](https://www.geeksforgeeks.org/tcp-ip-in-computer-networking/)
- [https://csc-knu.github.io/sys-prog/books/Andrew%20S.%20Tanenbaum%20-%20Computer%20Networks.pdf](https://csc-knu.github.io/sys-prog/books/Andrew%20S.%20Tanenbaum%20-%20Computer%20Networks.pdf)
- [https://www.ucg.ac.me/skladiste/blog_44233/objava_64433/fajlovi/Computer%20Networking%20_%20A%20Top%20Down%20Approach,%207th,%20converted.pdf](https://www.ucg.ac.me/skladiste/blog_44233/objava_64433/fajlovi/Computer%20Networking%20_%20A%20Top%20Down%20Approach,%207th,%20converted.pdf)
