## Giao thức cổng đường biên là gì?

Giao thức cổng đường biên (BGP) là một tập hợp các quy tắc xác định những tuyến mạng tốt nhất để truyền dữ liệu trên Internet. Internet bao gồm hàng nghìn mạng riêng, công cộng, của công ty và của chính phủ được liên kết với nhau thông qua các giao thức, thiết bị và công nghệ giao tiếp được chuẩn hóa. Khi bạn duyệt Internet, dữ liệu sẽ di chuyển qua nhiều mạng trước khi đến đích. Trách nhiệm của BGP là xem xét tất cả các đường dẫn sẵn sàng truyền dữ liệu và chọn tuyến tốt nhất. Ví dụ: Khi một người dùng ở Hoa Kỳ tải một ứng dụng có máy chủ gốc ở châu Âu, BGP sẽ giúp hoạt động giao tiếp đó diễn ra nhanh chóng và hiệu quả.

![[Pasted image 20260619160307.png]]

## Tại sao Giao thức cổng đường biên lại quan trọng?

Giao thức cổng đường biên (BGP) làm cho Internet hoạt động thông qua định tuyến dữ liệu. Định tuyến BGP rất quan trọng vì, về cốt lõi, Internet được tạo thành từ hàng trăm nghìn hệ thống tự trị.

Hệ thống tự trị là một mạng nhỏ hơn thuộc sự kiểm soát của một thực thể quản trị duy nhất. Bạn có thể xác định các mạng đó một cách độc nhất bằng số hệ thống tự trị của chúng do Tổ chức cấp phát số hiệu Internet (IANA) chỉ định. Dữ liệu di chuyển giữa các hệ thống tự trị khi dữ liệu di chuyển từ nguồn đến đích.

BGP hỗ trợ mọi hệ thống tự trị trong các hoạt động sau.

### **Tìm tuyến tốt nhất**

Khi dữ liệu di chuyển qua Internet từ nguồn đến đích, mọi hệ thống tự trị ở giữa phải quyết định điểm đến tiếp theo của gói dữ liệu.

Quyết định này dựa trên một số yếu tố như vị trí địa lý, tắc nghẽn mạng và chi phí truyền dữ liệu. Định tuyến BGP xem xét các yếu tố này và giúp xác định hệ thống tự trị tốt nhất tiếp theo để dữ liệu di chuyển trên tuyến ngắn nhất từ nguồn đến đích.

### **Khám phá các thay đổi kết nối mạng**

Internet có cấu trúc động. Liên tục có các hệ thống tự trị mới được thêm vào và hệ thống tự trị cũ được loại bỏ. Mỗi hệ thống tự trị phải cập nhật thông tin liên quan đến các tuyến mới và tuyến lỗi thời. BGP giúp các hệ thống phát hiện và cập nhật những thay đổi mạng như vậy.

### **Quản trị các chính sách mạng**

BGP linh hoạt trong việc cho phép các quản trị viên hệ thống tự trị thực hiện các chính sách định tuyến của riêng họ.

Ví dụ: bạn có thể định cấu hình một bộ định tuyến chạy BGP để phân biệt giữa các tuyến nội bộ và bên ngoài hệ thống tự trị. Quản trị viên có thể thiết lập các quy tắc để xác định xem nên định tuyến dữ liệu nội bộ hay bên ngoài.

### **Thêm một lớp bảo mật mạng**

BGP hỗ trợ bảo mật trong quản lý mạng của bạn. Ví dụ: BGP có thể xác thực tin nhắn giữa các bộ định tuyến bằng mật khẩu được định cấu hình sẵn. Quản trị viên có thể xác minh thông điệp BGP đến từ các hệ thống tự trị hợp lệ và lọc ra lưu lượng truy cập trái phép.

## Giao thức cổng đường biên hoạt động như thế nào?

Giao thức cổng đường biên (BGP) hoạt động bằng cách sử dụng một cơ chế gọi là _kết nối ngang hàng_. Quản trị viên chỉ định một số bộ định tuyến làm bộ định tuyến ngang hàng BGP hoặc BGP phát tin. Bạn có thể hình dung bộ định tuyến ngang hàng như các thiết bị trên biên hoặc ranh giới của một hệ thống tự trị.

Các bộ định tuyến ngang hàng BGP thực hiện các chức năng chính sau đây.

### **Khám phá tuyến**

Bộ định tuyến ngang hàng BGP trao đổi thông tin định tuyến với các bộ định tuyến ngang hàng BGP lân cận thông qua thông tin tiếp cận lớp mạng (NLRI) và các thuộc tính đường dẫn. NLRI bao gồm thông tin kết nối về các bộ định tuyến lân cận. Thuộc tính đường dẫn bao gồm các thông tin như độ trễ, số bước nhảy và chi phí truyền.

Sau khi chúng trao đổi thông tin, mỗi bộ định tuyến ngang hàng BGP sau đó có thể xây dựng một đồ thị gồm các kết nối mạng xung quanh nó.

### **Lưu trữ tuyến**

Trong quá trình khám phá, mọi bộ định tuyến BGP thu thập thông tin quảng cáo tuyến và lưu trữ dưới dạng bảng định tuyến. Bảng định tuyến được sử dụng để lựa chọn đường dẫn và cũng được cập nhật thường xuyên.

Ví dụ: bộ định tuyến BGP nhận được thông điệp _duy trì hoạt động_ cứ mỗi 30 giây từ các bộ định tuyến lân cận. Bộ định tuyến này cập nhật các tuyến được lưu trữ tương ứng theo đó.

### **Lựa chọn đường dẫn**

Các bộ định tuyến BGP sử dụng thông tin được lưu trữ để định tuyến lưu lượng truy cập một cách tối ưu. Yếu tố chính trong lựa chọn đường dẫn là đường dẫn ngắn nhất, như được xác định theo các đồ thị tuyến được lưu trữ. Khi có thể tiếp cận một điểm đến từ nhiều đường dẫn, BGP chọn một đường dẫn tốt nhất bằng cách đánh giá tuần tự các thuộc tính đường dẫn khác.

## Giao thức cổng đường biên có những loại nào?

Giao thức cổng đường biên (BGP) được phân loại là nội bộ và bên ngoài, tùy thuộc vào vị trí dữ liệu đang được định tuyến.

Các bộ định tuyến BGP bên ngoài kết nối một hệ thống tự trị với Internet toàn cầu. Tuy nhiên, bản thân các hệ thống tự trị lớn được tạo thành từ các hệ thống tự trị nhỏ hơn bên trong chúng. BGP nội bộ định tuyến dữ liệu trong một hệ thống.

### **So sánh giữa BGP bên ngoài và BGP nội bộ**

Điểm khác biệt chính giữa kết nối ngang hàng BGP nội bộ và bên ngoài là đường đi mà tuyến BGP nhận được từ một bộ định tuyến ngang hàng sẽ được truyền theo mặc định cho bộ định tuyến ngang hàng khác. Giải thích như sau:

- Các tuyến mới được cho biết từ một bộ định tuyến ngang hàng BGP bên ngoài được quảng bá lại cho tất cả các bộ định tuyến ngang hàng
- Các tuyến mới được cho biết từ một bộ định tuyến ngang hàng BGP nội bộ được quảng bá lại chỉ cho tất cả các bộ định tuyến ngang hàng bên ngoài

Ngoài ra, các tổ chức phải sử dụng BGP bên ngoài để kết nối mạng công ty của họ với Internet.

Ngược lại, không cần phải sử dụng BGP nội bộ. Bạn có thể chọn từ nhiều giao thức định tuyến nội bộ dựa trên yêu cầu kết nối mạng của tổ chức bạn.

![](https://d2908q01vomqb2.cloudfront.net/5b384ce32d8cdef02bc3a139d4cac0a22bb029e8/2020/07/29/eng-hybrid-trafficflows-vifs.png)

## Giao thức cổng đường biên xử lý quy mô như thế nào?

Khi hàng triệu thiết bị được kết nối với Internet, làm thế nào để một bộ định tuyến Giao thức cổng đường biên (BGP) có thể kết nối với hàng nghìn bộ định tuyến ngang hàng tiềm năng? Một số cách tiếp cận được sử dụng để quản lý quy mô và đáp ứng được sự mở rộng của Internet. Việc chia nhỏ được sử dụng ở mọi cấp độ để đảm bảo vẫn có thể quản lý được số lượng bộ định tuyến ngang hàng mà mỗi bộ định tuyến phải ghi nhớ.

Tiếp theo, chúng ta sẽ thảo luận về một số cách mà BGP xử lý quy mô.

### **Bộ phản xạ tuyến**

Bộ phản xạ tuyến (RR) làm giảm số lượng kết nối trong BGP nội bộ. Một bộ định tuyến đơn lẻ có thể hoạt động như một trung tâm kết nối ngang hàng với một cụm bộ định tuyến nội bộ.

Bạn có thể chia nhỏ mạng của mình thành nhiều cụm và RR. Chỉ có RR giao tiếp với nhau và với các bộ định tuyến BGP bên ngoài.

### **Liên minh**

Tất cả bộ định tuyến BGP bên ngoài đều không được kết nối với mọi bộ định tuyến BGP bên ngoài khác trên toàn thế giới. Thay vào đó là sử dụng các liên minh. Liên minh là một tập hợp các hệ thống tự trị có Số hệ thống tự trị (ASN) duy nhất mà phần còn lại của Internet có thể nhìn thấy.

Ví dụ: các nhà cung cấp dịch vụ Internet (ISP) của một số quốc gia châu Âu có thể tập hợp lại với nhau để tạo thành một liên minh châu Âu. Phần còn lại của thế giới sẽ thấy một ASN duy nhất cho nhiều quốc gia.

### **Tổng hợp tuyến**

Bộ phản xạ tuyến và các liên minh giúp giảm số lượng mạng BGP toàn cầu. Tuy nhiên, cấp độ cao nhất của các bộ định tuyến ngang hàng toàn cầu cũng đang tăng lên theo cấp số nhân.

Với nỗ lực ngăn chặn sự chia nhỏ kết nối rộng khắp có thể xảy ra, các ISP hợp tác để giữ cho bảng định tuyến toàn cầu ở quy mô nhỏ nhất có thể. Họ sử dụng Định tuyến liên miền không phân lớp (CIDR) để phân bổ địa chỉ IP hiệu quả hơn. Họ cũng sử dụng tổng hợp tuyến để đại diện cho nhiều mạng trong một mục bảng định tuyến duy nhất.

[Tìm hiểu về CIDR »](https://aws.amazon.com/what-is/cidr/)

## AWS có thể hỗ trợ các yêu cầu giao thức định tuyến BGP của bạn như thế nào?

Amazon Web Services (AWS) cung cấp [AWS Transit Gateway](https://aws.amazon.com/transit-gateway/) và [AWS Direct Connect](https://aws.amazon.com/directconnect/) để hỗ trợ các yêu cầu về giao thức định tuyến Giao thức cổng biên giới (BGP) của bạn.

### **Cổng chuyển tiếp**

Cổng chuyển tiếp kết nối Đám mây riêng ảo (VPC) Amazon và hệ thống mạng tại chỗ thông qua trung tâm. Kết nối này giúp đơn giản hóa hệ thống mạng của bạn và chấm dứt các quan hệ ngang hàng phức tạp.

Cổng chuyển tiếp hoạt động như một bộ định tuyến đám mây có quy mô linh hoạt – mỗi kết nối mới chỉ được tạo một lần. Cổng chuyển tiếp hỗ trợ BGP đơn giản hóa kết nối nhánh thông qua tích hợp gốc các thiết bị mạng ảo. Bất kỳ thiết bị bên thứ ba nào hỗ trợ BGP đều hoạt động với Cổng chuyển tiếp.

### **AWS Direct Connect**

Tương tự, AWS Direct Connect là đường dẫn ngắn nhất đến các tài nguyên AWS của bạn. Trong khi chuyển tiếp, lưu lượng mạng của bạn vẫn ở trên mạng toàn cầu AWS và không dùng đến Internet công cộng.

Bạn có thể sử dụng cổng AWS Direct Connect được gán với một hay nhiều giao diện ảo chuyển tiếp để giao tiếp với tối đa ba cổng chuyển tiếp trong bất kỳ Khu vực AWS được hỗ trợ nào. Bạn có thể thiết lập một phiên IPv4 BGP và một phiên IPv6 BGP trên một giao diện ảo chuyển tiếp.

Bắt đầu với định tuyến BGP giữa tài nguyên AWS và mạng công ty của bạn bằng cách [tạo tài khoản ngay](https://portal.aws.amazon.com/billing/signup) hôm nay.