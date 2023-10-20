# Which IP ranges/subnets are "private" or "non-routable" (RFC 1918)?

Theo RFC 1918, các dải địa chỉ IP "private" hoặc "non-routable" được sử dụng bên trong mạng nội bộ và không được định tuyến trực tiếp qua Internet. Dưới đây là danh sách các dải địa chỉ IP private theo RFC 1918:

1. 10.0.0.0 - 10.255.255.255 (CIDR: 10.0.0.0/8)
2. 172.16.0.0 - 172.31.255.255 (CIDR: 172.16.0.0/12)
3. 192.168.0.0 - 192.168.255.255 (CIDR: 192.168.0.0/16)

Các địa chỉ IP trong các dải này thường được sử dụng cho mạng nội bộ, intranet, và các môi trường không cần phải truy cập trực tiếp từ Internet. Nếu bạn cấu hình một mạng nội bộ, bạn có thể sử dụng các dải này để gán địa chỉ IP cho các thiết bị trong mạng của bạn mà không cần lo lắng về xung đột với địa chỉ IP trên Internet.