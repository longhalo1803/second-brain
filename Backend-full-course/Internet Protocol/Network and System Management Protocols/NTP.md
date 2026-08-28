# 1) Giới thiệu:

- Giao thức NTP (Network Time Protocol) là một giao thức để đồng bộ đồng hồ của các hệ thống máy tính thông qua mạng dữ liệu chuyển mạch gói với độ trễ biến đổi. Giao thức này được thiết kế để tránh ảnh hưởng của độ trễ biến đổi bằng cách sử dụng bộ đệm jitter. NTP cũng là tên gọi của phần mềm được triển khai trong dự án Dịch vụ NTP Công cộng (NTP Public Services Project).
- NTP là một trong những giao thức Internet lâu đời nhất vẫn còn được sử dụng (từ trước năm 1985). NTP được thiết kế đầu tiên bởi Dave Mills tại trường đại học Delaware, hiện ông vẫn còn quản lý nó cùng với một nhóm người tình nguyện.
- Để một hệ thống hoạt động và có thể phối hợp được với nhau điều kiện tiên quyết đầu tiên là giữa các hệ thống đó phải đồng bộ được về mặt thời gian. Nhờ vậy mà các bộ phận điều khiển có thể điều kiển được các bộ phận khác. Khi một hệ thống mất đồng bộ về mặt thời ngay lập tức hệ thống đó sẽ không hoạt động được nữa.
- NTP sử dụng thuật toán Marzullo, và nó cũng hỗ trợ các tính năng như giây nhuận. NTPv4 thông thường có thể đảm bảo độ chính xác trong khoảng 10 mili giây (1/100s) trên mạng Internet công cộng, và có thể đạt đến độ chính xác 200 micro giây (1/5000s) hay hơn nữa trong điều kiện lý tưởng của môi trường mạng cục bộ.
- Trên mạng Internet, NTP đồng bộ đồng hồ của các hệ thống máy tính theo UTC; trong môi trường LAN độc lập, NTP cũng thường được sử dụng để đồng bộ với UTC, nhưng về nguyên tắc nó có thể được sử dụng để đồng bộ với một mốc thời gian khác, ví dụ như múi giờ tại chỗ.
- Chi tiết hoạt động của NTP được quy định trong các RFC 778, RFC 891, RFC 956, RC 958 (thay thế bởi 1305), và RFC 1305 . Chuẩn đang được triển khai là phiên bản 4 (NTPv4 ); tuy nhiên, vào năm 2005, chỉ có phiên bản 3 và các phiên bản cũ hơn được quy định trong các RFCs. Tổ chức IETF NTP Working Group đã chuẩn hóa hoạt động của cộng đồng NTP từ khi có RFC 1305.
- Một phiên bản đơn giản hơn của NTP không cần yêu cầu lưu trữ thông tin trao đổi cũ được gọi là Giao thức Đồng bộ Thời gian mạng đơn giản - Simple Network Time Protocol hay SNTP. Giao thức này được sử dụng cho các thiết bị nhúng và trong các ứng dụng không cần độ chính xác cao về thời gian (Xem các RFC 1369, RFC 1769, RFC 2030 và RFC 4330).
- Chú ý rằng NTP chỉ cung cấp thời gian UTC, và không có thông tin về múi giờ hay giờ tiết kiệm ánh sáng ngày (Daylight saving time). Thông tin này nằm ngoài hoạt động của NTP và được xác định bằng cách khác (hầu hết các hệ thống đều cho phép chỉnh các thông số này).

# 2) Phương thức hoạt động:

![](https://images.viblo.asia/0d47264b-7660-445d-8d4b-7dd2c9a6140c.png)

- NTP client gửi một gói tin, trong đó chứa một thẻ thời gian tới cho NTP server.
- NTP server nhận được gói tin, gửi trả lại NTP client một gói tin khác, có thẻ thời gian là thời điểm nó gửi gói tin đó đi.
- NTP client nhận được gói tin đó, tính toán độ trễ, dựa và thẻ thời gian mà nó nhận được cùng với độ trễ đường truyền, NTP client sẽ set lại thời gian của nó.

# 3) Các câu lệnh NTP:

- Câu lệnh date được dùng để truy cập và thiết lập đồng hồ hệ thống:

```none
$ date
Sat Dec 30 18:46:53 ICT 2017
```

- Chúng ta có thể thiết lập định dạng thời gian cho câu lệnh date với tùy chọn “+”:

```none
$ date '+%D %T'
12/30/17 18:48:49
```

- Ta cũng có thể hiển thị các ngày khác với ngày hiện thời:

```none
$ date -d 'yesterday'
Fri Dec 29 18:51:08 ICT 2017
```

- hwclock là câu lệnh dùng để kiểm soat đông hồ phần cứng do BIOS quản lý. Khi dùng date để thay đổi giờ thì đồng hồ phần cứng sẽ không bị ảnh hưởng, do đó tại lần khởi động máy kế tiếp, hệ thống sẽ lấy thông tin thời gian từ đồng hồ phần cứng. Để dùng câu lệnh hwclock, ta phải dùng account root.

```none
$ hwclock
Sat 30 Dec 2017 07:21:57 PM ICT .962794 seconds
```

- Đồng hồ phần cứng có thể được thiết lập theo thời gian của vùng bạn ở hay theo UTC. Khi hệ thống khởi động, đồng hồ hệ thống sẽ lấy giá trị từ đồng hồ phần cứng bằng một trong hai câu lệnh sau:

```none
hwclock --hctosys --utc        # BIOS clock is UTC
hwclock --hctosys --localtime  # BIOS clock is local time
```

- Thiết lập giờ hiện tại và giờ hệ thống (BIOS):

```none
hwclock –-hctosys // set đồng hồ hệ thống (BIOS) cho đồng hồ hiện tại
hwclock --systohc // ngược với hctosys
```

- Tùy theo phiên bản Linux, ta cần thay đổi một trong những file sau để thiết lập thời gian, tìm ra timezone của hệ thống:

```none
/etc/sysconfig/clock   # Redhat, newer SuSE – HWCLOCK value
/etc/rc.config         # SuSE – GMT value
/etc/defaults/rcS      # Debian – UTC value
```

# 4) Kiểm tra và cài đặt NTP:

- Kiểm tra xem ntp có chạy không:

```none
$ ps -ef | grep ntp
root 3275 3112 0 16:07 pts/2 00:00:00 vi /etc/ntp.conf
ntp 3557 1 0 17:27 ? 00:00:00 ntpd -u ntp:ntp -p /var/run/ntpd.pid -g
root 3563 3402 0 17:27 pts/3 00:00:00 grep ntp
```

- Cài đặt NTP: `$ yum -y install ntp`
- Làm việc với ntpd bằng các lệnh:

```none
$ service ntpd stop
$ service ntpd start
$ service ntpd restart
$ service ntpd status
```

- File cấu hình mặc định:

```none
$ /etc/ntp.conf
restrict default kod nomodify notrap nopeer noquery
restrict -6 default kod nomodify notrap nopeer noquery
restrict 127.0.0.1
restrict -6 ::1
server 0.rhel.pool.ntp.org
server 1.rhel.pool.ntp.org
server 2.rhel.pool.ntp.org
server 127.127.1.0 # local clock
fudge 127.127.1.0 stratum 10
driftfile /var/lib/ntp/drift
keys /etc/ntp/keys
```

- Mặc định sẽ có 1 số NTP server trong file ntp.conf. Bạn cũng có thể thêm server NTP tùy vào khu vực và mục đích hệ thống của bạn. Ví dụ:

```none
server 0.asia.pool.ntp.org
server 1.asia.pool.ntp.org
server 2.asia.pool.ntp.org
server 3.asia.pool.ntp.org
```

- Tham khảo thêm về một số NTP server trên thế giới : [http://www.pool.ntp.org/en/](http://www.pool.ntp.org/en/), NTP Servers tại Châu Á: [http://www.pool.ntp.org/zone/asia](http://www.pool.ntp.org/zone/asia)
- Kiểm tra NTP làm việc:

```none
# sudo ntpq -p
     remote           refid      st t when poll reach   delay   offset  jitter
==============================================================================
+stratum2-2.NTP. 129.70.130.70    2 u    5   64  377   68.461  -44.274 110.334
+ntp2.m-online.n 212.18.1.106     2 u    5   64  377   54.629  -27.318  78.882
*145.253.66.170  .DCFa.           1 u   10   64  377   83.607  -30.159  68.343
+stratum2-3.NTP. 129.70.130.70    2 u    5   64  357   68.795  -68.168 104.612
+europium.canoni 193.79.237.14    2 u   63   64  337   81.534  -67.968  92.792
```

- Cập nhật thời gian tại một server khác: `ntpdate –q <địa chỉ time_server>`