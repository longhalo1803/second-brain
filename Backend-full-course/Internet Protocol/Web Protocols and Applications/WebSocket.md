
# Lý thuyết 

### 1. WebSocket là gì?

WebSocket là một giao thức truyền tải dữ liệu cho phép thiết lập kết nối **hai chiều (bidirectional)** và **liên tục (persistent)** giữa máy khách (client) và máy chủ (server) trên một kết nối duy nhất.

![[Pasted image 20260622091742.png]]

Nếu HTTP giống như một chiếc xe phải dừng lại ở mọi ngã tư để hỏi đường (mô hình request-response truyền thống), thì WebSocket giống như một **đường cao tốc riêng không có đèn đỏ**, nơi dữ liệu có thể trôi chảy tự do giữa trình duyệt và máy chủ mà không cần phải thiết lập kết nối lại.

### 2. Sự khác biệt cốt lõi: HTTP vs WebSocket

- **HTTP (Request-Response):** Là mô hình yêu cầu - phản hồi. Mỗi lần bạn muốn lấy dữ liệu mới, bạn phải gửi một request và chờ server phản hồi. Điều này gây ra độ trễ (latency) không cần thiết khi cần dữ liệu cập nhật liên tục.
    
- **WebSocket:** Sau khi kết nối được thiết lập, dữ liệu được gửi qua lại ngay lập tức mà không cần gửi các header HTTP dư thừa cho mỗi tin nhắn, giúp hệ thống hoạt động mượt mà và tiết kiệm băng thông.
    

### 3. Cách thức hoạt động

Quá trình thiết lập kết nối WebSocket rất đặc biệt:

- **Khởi tạo:** Nó bắt đầu bằng một cú bắt tay (handshake) thông qua một yêu cầu HTTP thông thường.
    
- **Nâng cấp (Upgrade):** Khi server hiểu đó là yêu cầu WebSocket, nó sẽ "nâng cấp" kết nối đó từ HTTP lên thành một kênh kết nối WebSocket bền vững.
    
- **Duy trì:** Sau khi "nâng cấp", kết nối này không đóng lại cho đến khi một trong hai bên chủ động ngắt kết nối.
    

### 4. Bảo mật với WSS

Cũng giống như HTTP có HTTPS để bảo mật, WebSocket có **WSS (WebSocket Secure)**.

- WSS là phiên bản đã được mã hóa của WebSocket, đảm bảo dữ liệu truyền tải giữa client và server không thể bị nghe lén hay can thiệp bởi bên thứ ba. Đây là tiêu chuẩn bắt buộc nếu bạn muốn truyền tải thông tin nhạy cảm qua giao thức này.
    

### 5. Tại sao cần WebSocket? (Use cases)

Trước khi có WebSocket, lập trình viên phải sử dụng các kỹ thuật "hack" như _long polling_ (gửi request liên tục) để giả lập tính thời gian thực. WebSocket ra đời (tiêu chuẩn hóa năm 2011) đã thay thế hoàn toàn các phương thức đó. Các ứng dụng điển hình bao gồm:

- **Live Chat:** Gửi và nhận tin nhắn tức thời.
    
- **Game nhiều người chơi (Multiplayer Games):** Nơi tốc độ cập nhật trạng thái nhân vật là yếu tố sống còn.
    
- **Theo dõi chứng khoán (Stock tickers):** Cập nhật giá liên tục mà không cần F5 trình duyệt.
    
- **Các ứng dụng cộng tác:** Google Docs hoặc các công cụ chỉnh sửa văn bản thời gian thực.
    

**Tóm lại:** WebSocket là giải pháp tối ưu cho bất kỳ bài toán nào cần sự tương tác thời gian thực giữa máy chủ và người dùng. Là một lập trình viên Back-end, nắm vững cách vận hành và bảo mật (WSS) của WebSocket sẽ giúp bạn xây dựng được những hệ thống có trải nghiệm người dùng mượt mà và chuyên nghiệp hơn nhiều.


# Web Socket API

### Kiểm tra trình duyệt có hỗ trợ WebSockets hay không

Việc đầu tiên cần làm khi làm việc với WebSockets trên client là kiểm tra WebSockets có được trình duyệt hỗ trợ hay không:

```none
if ('WebSocket' in window) {
   /* WebSocket is supported. You can proceed with your code*/
} else {
   /*WebSocket
}
```

### Đóng/mở WebSockets

Giả sử trình duyệt hỗ trợ WebSockets, chúng ta bắt đầu khởi tạo và mở socket.

**Khởi tạo WebSockets**

```none
var connection = new WebSocket('ws://example.org:12345/myapp');
```

**hoặc với WebSockets secure**

```none
var connection = new WebSocket('wss://example.org:12345/myapp');
```

**Mở connection đến server**

```none
connection.onopen = function(){
   /*Send a small message to the console once the connection is established */
   console.log('Connection open!');
}
```

**Đóng WebSockets**

```none
connection.onclose = function(){
   console.log('Connection closed');
}
```

hoặc

```none
connection.close();
```

**Ngoài ra, chúng ta cũng có thể kiểm tra trường hợp có lỗi xảy ra**

```none
connection.onerror = function(error){
   console.log('Error detected: ' + error);
}
```

## Gửi – nhận message

**Gửi message đến server**

```none
var message = {
'name': 'bill murray',
'comment': 'No one will ever believe you'
};
connection.send(JSON.stringify(message));
```

**Nhận message từ server**

```none
connection.onmessage = function(e){
   var server_message = e.data;
   console.log(server_message);
}
```