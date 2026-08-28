## Những điểm chính

- **Giao thức TLS là gì:** Biết được TLS là giao thức bảo mật nhằm bảo vệ tính riêng tư và bảo mật dữ liệu cho các giao tiếp qua Internet.
- **Mối quan hệ giữa TLS và SSL:** Phân biệt được sự khác nhau giữa TLS và SSL, hiểu được TLS là phiên bản nâng cấp và thay thế cho SSL. 
- **Tầm quan trọng:** Nhận thức rõ hơn về tầm quan trọng của TLS trong việc bảo vệ dữ liệu nhạy cảm, xác thực danh tính máy chủ và tạo dựng niềm tin cho người dùng. 
- **Nguyên lý và cách thức hoạt động:** Nắm được cách TLS hoạt động, bao gồm mô hình client-server, vai trò của chứng chỉ TLS và cơ chế mã hóa. 
- **Quá trình bắt tay TLS (TLS Handshake):** Hiểu được các bước chi tiết trong quá trình thiết lập kết nối an toàn giữa client và server. 
- **Các chức năng chính:** Nắm rõ các chức năng cốt lõi của TLS, bao gồm mã hóa, xác thực, bảo toàn tính toàn vẹn dữ liệu,..
- **Các phiên bản hiện hành:** Phân biệt được các phiên bản TLS khác nhau, hiểu được phiên bản nào đang được khuyến nghị sử dụng và tại sao. 
- **So sánh chi tiết SSL và TLS:** Nắm được điểm tương đồng và khác biệt giữa SSL và TLS. 
- **TLS và HTTPS: Khác biệt và mối liên hệ:** Hiểu rõ mối quan hệ giữa TLS và HTTPS, hiểu được HTTPS là HTTP được bảo mật bằng TLS. 
- **Ảnh hưởng của TLS đến hiệu suất website:** Hiểu được ảnh hưởng của TLS đến hiệu suất website và các công nghệ giảm thiểu tác động này. 
- **Giới thiệu Vietnix:** Là nhà cung cấp dịch vụ SSL uy tín. 
- **Câu hỏi thường gặp:** Có câu trả lời nhanh cho các câu hỏi thường gặp về SSL/TLS.

## **TLS là gì?**

TLS (Transport Layer Security) là một giao thức bảo mật được sử dụng rộng rãi, nhằm bảo vệ tính riêng tư và bảo mật dữ liệu cho các giao tiếp qua Internet. Đây là phiên bản nâng cấp và cải tiến của giao thức SSL (Secure Sockets Layer), với khả năng [mã hóa](https://vietnix.vn/ma-hoa-la-gi/) mạnh mẽ và cơ chế xác thực đáng tin cậy. 

![Giao thức TLS là gì?](https://static.vietnix.vn/wp-content/uploads/2024/06/tls-la-gi.webp "TLS là gì? Chức năng, cách thức hoạt động và tầm quan trọng của Transport Layer Security 12")

Giao thức TLS là gì?

Chức năng chính của TLS là mã hóa và xác thực dữ liệu giữa các ứng dụng, máy chủ, người dùng và hệ thống. Giao thức này được ứng dụng rộng rãi, đặc biệt trong việc tạo ra các kết nối an toàn thông qua giao thức HTTPS, thường được biểu thị bằng biểu tượng khóa trong trình duyệt web khi một phiên kết nối an toàn được thiết lập. Ngoài ra, TLS còn được sử dụng để mã hóa các giao tiếp khác như email, tin nhắn và thoại qua IP ([VoIP](https://vietnix.vn/voip-la-gi/)).

## **Mối quan hệ giữa TLS và [[SSL]]**

TLS (Transport Layer Security) là phiên bản nâng cấp và thay thế cho giao thức SSL (Secure Sockets Layer). Cụ thể, TLS 1.0 được phát triển dựa trên SSL 3.0, kế thừa và cải tiến những điểm yếu bảo mật của SSL. Mặc dù TLS đã thay thế hoàn toàn SSL, thuật ngữ “SSL” vẫn thường được sử dụng thay thế cho “TLS” hoặc kết hợp thành “SSL/TLS” ngay cả khi thực tế đang đề cập đến TLS. 

Hiện nay, phiên bản TLS phổ biến nhất là TLS 1.3, đóng vai trò quan trọng trong việc đảm bảo an toàn thông tin trên internet, ngăn chặn việc đánh cắp hoặc thay đổi dữ liệu bởi các cuộc tấn công mạng. Mặc dù chứng chỉ thường được gọi là “chứng chỉ SSL”, nhưng thực tế hiện nay tất cả đều là chứng chỉ TLS, hỗ trợ cả giao thức TLS và SSL (mặc dù SSL đã không còn được khuyến nghị sử dụng).

![Mối quan hệ giữa TLS/SSL](https://static.vietnix.vn/wp-content/uploads/2024/06/ssl-vs-tls.webp "TLS là gì? Chức năng, cách thức hoạt động và tầm quan trọng của Transport Layer Security 13")

Mối quan hệ giữa TLS/SSL

## Tại sao TLS lại quan trọng?

TLS đóng vai trò cực kỳ quan trọng trong việc bảo mật thông tin khi truyền qua Internet. Trước hết, nó sử dụng công nghệ mã hóa mạnh mẽ để ngăn chặn kẻ tấn công nghe lén hoặc đánh cắp các dữ liệu nhạy cảm như mật khẩu, thông tin tài khoản ngân hàng hoặc thông tin cá nhân. 

Giao thức này cũng đảm bảo rằng người dùng đang kết nối với đúng máy chủ thông qua quá trình xác thực bằng chứng chỉ kỹ thuật số, giúp phòng tránh các cuộc tấn công giả mạo hoặc lừa đảo từ các trang web không đáng tin cậy.

TLS còn cung cấp các cơ chế kiểm tra nhằm đảm bảo tính toàn vẹn của dữ liệu trong suốt quá trình truyền, từ đó ngăn chặn các cuộc tấn công trung gian (Man-in-the-Middle – MITM). 

Ngoài ra, biểu tượng ổ khóa và tiền tố “https://” trên trình duyệt là dấu hiệu nhận biết kết nối an toàn, góp phần tạo dựng lòng tin cho người dùng. Không những thế, việc triển khai TLS còn giúp các tổ chức tuân thủ các tiêu chuẩn bảo mật nghiêm ngặt trong lĩnh vực công nghệ thông tin.

Để trang bị lớp bảo mật thiết yếu này cho website của bạn, việc [mua SSL](https://vietnix.vn/mua-ssl/) là bước không thể thiếu. Vietnix cung cấp dịch vụ chứng chỉ SSL chất lượng cao, đa dạng lựa chọn và hỗ trợ kỹ thuật chuyên nghiệp, giúp bạn dễ dàng triển khai TLS và bảo vệ dữ liệu khách hàng một cách hiệu quả. Hãy tìm hiểu thêm về dịch vụ mua SSL của Vietnix ngay hôm nay để tăng cường bảo mật và nâng cao uy tín cho website của bạn.

## **Nguyên lý và cách thức hoạt động của TLS**

TLS được sử dụng rộng rãi để bảo vệ các giao dịch trực tuyến, bao gồm mua sắm trực tuyến, truyền tải dữ liệu nhạy cảm (như mật khẩu và thông tin tài khoản) và email/tin nhắn. Giao thức này hoạt động dựa trên mô hình client-server và tuân thủ các tiêu chuẩn an ninh nghiêm ngặt, liên tục được cập nhật để chống lại các mối đe dọa bảo mật mới nhất.

### **Mô hình hoạt động Client-Server**

TLS hoạt động theo mô hình client-server, nơi client và [server](https://vietnix.vn/server-la-gi/) thiết lập kết nối an toàn. Quá trình này bao gồm nhiều bước, bắt đầu từ việc đàm phán phiên bản TLS, trao đổi thông tin mở rộng (nếu cần), xác thực chứng chỉ, trao đổi khóa và cuối cùng là thiết lập kết nối bảo mật để truyền dữ liệu mã hóa.

### **Vai trò của chứng chỉ TLS (SSL Certificate)**

Trong quá trình thiết lập kết nối, server gửi chứng chỉ TLS (thường bị gọi nhầm là chứng chỉ SSL) cho client. Chứng chỉ này chứa thông tin về danh tính của server (chủ sở hữu) và khóa công khai của nó. Client sẽ kiểm tra tính hợp lệ của chứng chỉ này bằng cách đối chiếu với cơ quan chứng nhận (CA) đáng tin cậy. Việc này đảm bảo client đang kết nối đến đúng server, không phải máy chủ giả mạo.

### **Cơ chế mã hóa (Khóa công khai và khóa đối xứng)**

TLS sử dụng kết hợp cả mã hóa bất đối xứng (khóa công khai – [public key](https://en.wikipedia.org/wiki/Public-key_cryptography)) và mã hóa đối xứng. Trong giai đoạn bắt tay (handshake), mã hóa bất đối xứng được sử dụng để trao đổi khóa bí mật một cách an toàn. Sau khi handshake hoàn tất, một khóa đối xứng (session key) được tạo ra và được sử dụng để mã hóa dữ liệu truyền tải trong suốt phiên kết nối. Việc sử dụng mã hóa đối xứng cho phép truyền dữ liệu lớn một cách hiệu quả hơn so với mã hóa bất đối xứng.

![Cách thức hoạt động của giao thức TLS](https://static.vietnix.vn/wp-content/uploads/2021/05/cach-thuc-hoat-dong-cua-tls.webp "TLS là gì? Chức năng, cách thức hoạt động và tầm quan trọng của Transport Layer Security 14")

Cách thức hoạt động của giao thức TLS

## Tìm hiểu quá trình bắt tay TLS (TLS Handshake) chi tiết

Quá trình bắt tay TLS (TLS Handshake) là bước thiết lập quan trọng cho một kết nối an toàn giữa client và server. Trong quá trình này, cả hai bên đồng ý về phiên bản TLS, bộ mã hóa (cipher suite) sẽ sử dụng, xác thực server (và đôi khi cả client) và tạo ra khóa phiên (session key) để mã hóa dữ liệu.

### **Mục đích của TLS Handshake**

Mục đích chính của TLS Handshake là khởi tạo và thiết lập một kết nối an toàn giữa client và server. Cụ thể hơn, handshake thực hiện các nhiệm vụ sau:

- **Đàm phán phiên bản TLS:** Client và server thống nhất phiên bản TLS sẽ được sử dụng cho kết nối.
- **Chọn Cipher Suite:** Xác định bộ thuật toán mã hóa, xác thực và trao đổi khóa sẽ được sử dụng.
- **Xác thực Server (và tùy chọn Client):** Đảm bảo danh tính của server (và đôi khi cả client) là chính xác.
- **Tạo Session Key:** Thiết lập khóa bí mật chung để mã hóa dữ liệu truyền tải sau khi handshake hoàn tất.

### **Các bước trong quá trình TLS Handshake** 

Dưới đây là các bước chi tiết trong một quá trình TLS Handshake điển hình:

1. **ClientHello:** Client gửi thông điệp “ClientHello” đến server. Thông điệp này chứa thông tin về phiên bản TLS mà client hỗ trợ, danh sách các cipher suite mà client có thể sử dụng, và một số ngẫu nhiên (client random).
2. **ServerHello:** Server phản hồi với thông điệp “ServerHello”. Thông điệp này chứa phiên bản TLS được chọn, cipher suite được chọn, một số ngẫu nhiên của server (server random), và chứng chỉ kỹ thuật số của server.
3. **Certificate:** Server gửi chứng chỉ kỹ thuật số của mình cho client. Chứng chỉ này chứa khóa công khai của server và được sử dụng để xác thực danh tính của server.
4. **Client Key Exchange:** Client kiểm tra tính hợp lệ của chứng chỉ server. Nếu chứng chỉ hợp lệ, client tạo ra một “pre-master secret”, mã hóa nó bằng khóa công khai của server, và gửi nó cho server.
5. **Server Key Exchange (Optional):** Bước này chỉ xảy ra nếu cipher suite yêu cầu trao đổi thêm thông tin khóa.
6. **Server Hello Done:** Server gửi thông điệp “Server Hello Done” để báo hiệu đã hoàn tất việc gửi thông tin cấu hình.
7. **Client Change Cipher Spec:** Client gửi thông báo “Change Cipher Spec” để báo hiệu sẽ bắt đầu sử dụng mã hóa đối xứng với session key.
8. **Client Finished:** Client gửi thông điệp “Finished”, được mã hóa bằng session key, để xác nhận đã hoàn tất handshake.
9. **Server Change Cipher Spec:** Server gửi thông báo “Change Cipher Spec” để báo hiệu sẽ bắt đầu sử dụng mã hóa đối xứng với session key.
10. **Server Finished:** Server gửi thông điệp “Finished”, được mã hóa bằng session key, để xác nhận đã hoàn tất handshake.

### **Bộ mã hóa (Cipher Suite)**

Bộ mã hóa (Cipher Suite) là một tập hợp các thuật toán mã hóa, xác thực, và trao đổi khóa được sử dụng trong một phiên TLS. Client và server đàm phán và thống nhất một cipher suite trong quá trình handshake. Cipher suite xác định các thuật toán cụ thể sẽ được sử dụng cho từng chức năng bảo mật trong kết nối TLS.

## **Các chức năng chính của giao thức TLS**

Giao thức TLS cung cấp một loạt các chức năng bảo mật quan trọng để bảo vệ thông tin liên lạc trực tuyến.

### **Mã hóa dữ liệu (Encryption)**

TLS sử dụng mã hóa để bảo vệ dữ liệu truyền giữa hai bên (thường là client và server). Dữ liệu được chuyển đổi thành dạng không thể đọc được bởi các bên thứ ba, đảm bảo chỉ người nhận dự định mới có thể giải mã và đọc thông tin.

### **Xác thực (Authentication – Server và Client)**

TLS hỗ trợ xác thực danh tính của cả server và client. Server sử dụng chứng chỉ số để chứng minh danh tính của mình với client. Client kiểm tra chứng chỉ này với CA đáng tin cậy để đảm bảo server là hợp pháp. Một số trường hợp, client cũng có thể được yêu cầu xác thực bằng chứng chỉ của mình.

![Chức năng transport layer security là gì?](https://static.vietnix.vn/wp-content/uploads/2024/06/chuc-nang-tls.webp "TLS là gì? Chức năng, cách thức hoạt động và tầm quan trọng của Transport Layer Security 15")

Chức năng transport layer security là gì?

### **Bảo toàn tính toàn vẹn dữ liệu (Data Integrity)**

TLS đảm bảo tính toàn vẹn của dữ liệu bằng cách sử dụng mã xác thực thông báo (MAC) hoặc hàm băm (hash). Một MAC hoặc hash được tính toán dựa trên dữ liệu được gửi. Bên nhận sẽ thực hiện tính toán tương tự và so sánh kết quả. Nếu dữ liệu bị thay đổi trong quá trình truyền, MAC hoặc hash sẽ không khớp và kết nối sẽ bị hủy.

### **Ngăn chặn tấn công phát lại (Replay Prevention)**

TLS sử dụng các biện pháp như số thứ tự (sequence number) hoặc dấu thời gian để ngăn chặn tấn công phát lại. Bằng cách này, kẻ tấn công không thể ghi lại và gửi lại các gói tin cũ để thực hiện các hành động trái phép.

### **Quản lý phiên (Session Management)**

TLS quản lý các phiên kết nối an toàn, sử dụng session key để mã hóa dữ liệu. TLS cũng hỗ trợ “Session Resumption”, cho phép tái sử dụng session key từ các kết nối trước đó, giúp cải thiện hiệu suất cho các kết nối sau này.

### **Ngăn chặn các kiểu tấn công**

TLS được thiết kế để bảo vệ chống lại nhiều kiểu tấn công, bao gồm tấn công trung gian (Man-in-the-Middle – MITM), giả mạo chứng chỉ và các tấn công phá mã (cipher attacks).

## Các phiên bản TLS hiện hành

### **TLS 1.0 (Phát hành 1999)**

Phiên bản đầu tiên của giao thức TLS, ra mắt năm 1999, là sự cải tiến từ SSL 3.0. Giao thức này cung cấp các tính năng cơ bản về mã hóa dữ liệu, xác thực và bảo vệ tính toàn vẹn. Tuy nhiên, theo thời gian, các lỗ hổng bảo mật đã được phát hiện và phiên bản này hiện không còn được coi là an toàn.

### **TLS 1.1 (Phát hành 2006)**

TLS 1.1 được phát hành năm 2006 như một bản nâng cấp của TLS 1.0. Giao thức này giới thiệu một số cải tiến về bảo mật, bao gồm cải thiện thuật toán xác thực, quản lý danh sách từ chối và hạn chế ủy quyền. Dù có những cải thiện, TLS 1.1 vẫn tồn tại vấn đề bảo mật và không được sử dụng rộng rãi trong các ứng dụng hiện đại.

### **TLS 1.2 (Phát hành 2008)**

Ra mắt năm 2008, TLS 1.2 là một phiên bản quan trọng với nhiều cải tiến đáng kể. Giao thức này hỗ trợ các thuật toán mã hóa mạnh hơn, cải thiện tính toàn vẹn dữ liệu và xác thực, đồng thời có các biện pháp để ngăn chặn các cuộc tấn công như BEAST và CRIME. TLS 1.2 đã trở nên phổ biến trong các ứng dụng web hiện đại và hiện vẫn đang được sử dụng rộng rãi (các dịch vụ hiện đại thường hỗ trợ từ TLS 1.2 trở lên).

### **TLS 1.3 (Phát hành 2018)**

Là phiên bản mới nhất của TLS, ra mắt năm 2018, giao thức này tập trung vào việc tăng cường bảo mật và hiệu suất một cách đáng kể. TLS 1.3 loại bỏ các thuật toán cũ được coi là không an toàn, giảm số lượng giao tiếp mạng trong quá trình handshake (xuống còn 1-RTT hoặc thậm chí 0-RTT cho các kết nối tiếp theo), giúp tăng tốc độ thiết lập kết nối. Giao thức này cũng bổ sung các tính năng bảo mật tiên tiến như Forward Secrecy. 

Đây là phiên bản hiện đang được sử dụng và đặc biệt được khuyến nghị cho các ứng dụng và dịch vụ mới.

## So sánh chi tiết: SSL và TLS

### **Điểm tương đồng**

Cả [SSL](https://vietnix.vn/ssl-la-gi/) và TLS đều có chung mục đích là bảo vệ thông tin truyền thông trên mạng. Cụ thể:

- **Mã hóa và Xác thực:** Cả hai đều mã hóa dữ liệu truyền tải và xác thực danh tính của các bên tham gia kết nối.
- **Sử dụng Chứng chỉ Kỹ thuật số:** Cả hai đều sử dụng chứng chỉ kỹ thuật số trong quá trình bắt tay (handshake) để thiết lập kết nối mã hóa.
- **Ứng dụng trong HTTPS:** Cả hai đều được sử dụng để bảo mật giao thức [HTTPS](https://vietnix.vn/https-la-gi/).

![so sanh ssl va tls](https://static.vietnix.vn/wp-content/uploads/2024/06/so-sanh-ssl-va-tls.webp "TLS là gì? Chức năng, cách thức hoạt động và tầm quan trọng của Transport Layer Security 16")

So sánh SSL và TLS

### **Điểm khác biệt chính**

|Đặc điểm|SSL|TLS|
|---|---|---|
|Bắt tay (Handshake)|Kết nối rõ ràng, nhiều bước hơn.|Kết nối ngầm, ít bước hơn, nhanh hơn.|
|Thông báo cảnh báo|Gồm 2 loại: Cảnh báo, nghiêm trọng và không mã hóa.|Đa dạng hơn, có thêm thông báo đóng phiên, được mã hóa.|
|Xác thực thông báo|Sử dụng MD5 (không an toàn).|Sử dụng HMAC (an toàn hơn).|
|Bộ mã hóa (Cipher Suites)|Hỗ trợ thuật toán cũ, có lỗ hổng.|Sử dụng thuật toán nâng cao, an toàn hơn.|

### **Tình trạng sử dụng hiện tại**

- **SSL:** Tất cả các phiên bản SSL (SSL 2.0, SSL 3.0) đều **không còn được khuyến nghị sử dụng** do các lỗ hổng bảo mật nghiêm trọng.
- **TLS 1.0 và 1.1:** Tương tự, TLS 1.0 và 1.1 cũng **không còn được khuyến nghị sử dụng**.
- **TLS 1.2 và 1.3:** TLS 1.2 và 1.3 là các phiên bản **đang được sử dụng và khuyến nghị**. TLS 1.3 là phiên bản mới nhất và an toàn nhất.

Mặc dù nhiều người vẫn gọi là “chứng chỉ SSL”, nhưng thực tế các chứng chỉ hiện nay là chứng chỉ TLS và hỗ trợ cả hai giao thức (trong đó SSL đã bị loại bỏ, chỉ còn TLS được dùng).

## **TLS và [[HTTP - HTTPS]]: Khác biệt và mối liên hệ**

Mặc dù có liên quan chặt chẽ, HTTPS và TLS là hai khái niệm khác nhau. Hiểu được sự khác biệt và mối liên hệ giữa chúng là rất quan trọng.

### **HTTPS là gì?**

HTTPS (Hyper Text Transfer Protocol Secure) là phiên bản bảo mật của HTTP, sử dụng mã hóa TLS (hoặc SSL cũ hơn, không còn được khuyến nghị) để bảo vệ dữ liệu truyền tải giữa trình duyệt web và máy chủ web. HTTPS được biểu thị bằng tiền tố “https://” trong URL và biểu tượng khóa trên thanh địa chỉ của trình duyệt. Sự hiện diện của HTTPS cho người dùng biết rằng kết nối với trang web được mã hóa và an toàn.

### **Mối liên hệ giữa HTTPS và TLS**

Mối liên hệ giữa HTTPS và TLS rất đơn giản: HTTPS là HTTP được bảo mật bằng TLS. Nói cách khác, HTTPS là một triển khai của TLS trên giao thức HTTP. Bất kỳ trang web nào sử dụng HTTPS đều đang sử dụng mã hóa TLS để bảo vệ dữ liệu truyền tải. 

TLS cung cấp lớp bảo mật cho HTTP, giúp ngăn chặn việc nghe lén và đảm bảo tính toàn vẹn của dữ liệu. Vì lý do bảo mật, tất cả các trang web hiện đại đều nên sử dụng HTTPS. Trình duyệt web hiện đại cũng cảnh báo người dùng khi họ truy cập các trang web không sử dụng HTTPS.

![Mối liên hệ giữa HTTPS và TLS](https://static.vietnix.vn/wp-content/uploads/2024/06/tls-vs-https.webp "TLS là gì? Chức năng, cách thức hoạt động và tầm quan trọng của Transport Layer Security 17")

Mối liên hệ giữa HTTPS và TLS

## **Ảnh hưởng của TLS đến hiệu suất website**

Mặc dù TLS cung cấp bảo mật quan trọng cho các website nhưng cũng có thể ảnh hưởng đến hiệu suất. Tuy nhiên, các phiên bản TLS hiện đại đã giảm thiểu đáng kể tác động này.

### **Chi phí ban đầu và độ trễ tiềm ẩn**

Quá trình bắt tay TLS (handshake) yêu cầu nhiều lần trao đổi thông tin giữa client và server trước khi dữ liệu được truyền. Điều này tiêu tốn thời gian và tài nguyên tính toán, dẫn đến độ trễ tiềm ẩn trong thời gian tải trang. Client và server đều cần thực hiện các phép tính và phân bổ bộ nhớ cho quá trình handshake.

### **Các công nghệ giảm thiểu ảnh hưởng**

Một số công nghệ đã được phát triển để giảm thiểu độ trễ do TLS handshake gây ra:

- **TLS False Start:** Cho phép client và server bắt đầu truyền dữ liệu ứng dụng _trước khi_ handshake hoàn tất. Điều này giúp giảm thiểu thời gian chờ đợi.
- **TLS Session Resumption:** Cho phép client và server đã kết nối trước đó sử dụng một phiên bản handshake rút gọn, giảm thiểu thời gian và tài nguyên cần thiết.

### **Cải tiến hiệu suất trong TLS 1.3**

TLS 1.3 mang lại những cải tiến đáng kể về hiệu suất:

- **1-RTT Handshake:** TLS 1.3 giảm số lần trao đổi thông tin trong handshake xuống chỉ còn một lượt đi-lại (1-RTT), giảm đáng kể độ trễ.
- **0-RTT Handshake (Zero Round Trip Time Resumption):** Đối với các kết nối đã được thiết lập trước đó, TLS 1.3 cho phép handshake với 0 lượt đi-lại (0-RTT), giúp việc thiết lập kết nối gần như tức thời.

Nhờ những cải tiến này, TLS 1.3 rất nhanh và tác động đến thời gian tải trang là tối thiểu. Chi phí tính toán liên quan đến TLS hiện nay không còn đáng kể so với lợi ích bảo mật mà nó mang lại.

## Những thách thức của giao thức TLS

Có một số hạn chế khi không sử dụng xác thực an toàn hoặc khi quyết định giữa TLS và các giao thức bảo mật khác, chẳng hạn như IPsec. Đây là vài ví dụ:

- Vì TLS hoạt động ở Lớp 4 đến Lớp 7 của [mô hình OSI](https://vietnix.vn/mo-hinh-osi-la-gi/), trái ngược với Lớp 3, là trường hợp của IPsec, mỗi ứng dụng và mỗi luồng giao tiếp giữa máy khách và máy chủ phải thiết lập phiên TLS của riêng mình để đạt được lợi ích xác thực và mã hóa dữ liệu.
- Khả năng sử dụng TLS phụ thuộc vào việc mỗi ứng dụng có hỗ trợ hay không.
- Vì TLS được triển khai trên cơ sở từng ứng dụng để đạt mức độ chi tiết được cải thiện và khả năng kiểm soát đối với các phiên được mã hóa, nó phải trả giá bằng chi phí quản lý tăng lên.