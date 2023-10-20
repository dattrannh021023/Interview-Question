# How many NTP servers would you configure in your local ntp.conf?

Số lượng máy chủ NTP (Network Time Protocol) mà bạn nên cấu hình trong tệp cấu hình "ntp.conf" tùy thuộc vào mục đích và yêu cầu cụ thể của hệ thống bạn đang quản lý. Thông thường, bạn nên cấu hình ít nhất hai máy chủ NTP để đảm bảo tính tin cậy và độ chính xác cao trong việc đồng bộ thời gian của hệ thống. Số lượng máy chủ NTP có thể tăng lên nếu bạn muốn đảm bảo sự đối phó với sự cố hoặc sự cố xảy ra trên máy chủ NTP chính.

Một quy tắc thông thường là sử dụng ít nhất ba máy chủ NTP, trong đó hai là máy chủ NTP chính và một là máy chủ dự phòng. Điều này giúp đảm bảo tính tin cậy và sự ổn định của dịch vụ đồng bộ thời gian của hệ thống, đặc biệt khi bạn phụ thuộc vào chính xác thời gian cho các ứng dụng quan trọng.

Dưới đây là một ví dụ về cách cấu hình máy chủ NTP trong tệp "ntp.conf" với ba máy chủ:

```
server ntp-server1.example.com
server ntp-server2.example.com
server ntp-server3.example.com

```

Trong ví dụ này, "[ntp-server1.example.com](http://ntp-server1.example.com/)" và "[ntp-server2.example.com](http://ntp-server2.example.com/)" là hai máy chủ NTP chính, trong khi "[ntp-server3.example.com](http://ntp-server3.example.com/)" là máy chủ dự phòng. Nếu một trong các máy chủ chính gặp sự cố, hệ thống của bạn có thể tự động chuyển sang máy chủ dự phòng để duy trì tính tin cậy trong đồng bộ thời gian.