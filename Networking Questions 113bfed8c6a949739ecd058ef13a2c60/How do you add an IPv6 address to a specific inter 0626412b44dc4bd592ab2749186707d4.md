# How do you add an IPv6 address to a specific interface?

Để thêm một địa chỉ IPv6 vào một giao diện (interface) cụ thể trên Linux, bạn có thể sử dụng lệnh `ip` hoặc chỉnh sửa tệp cấu hình mạng. Dưới đây là cách thực hiện bằng cả hai cách:

**Sử dụng lệnh `ip`**:

1. Xác định tên của giao diện mà bạn muốn thêm địa chỉ IPv6. Ví dụ, giao diện Ethernet có thể là `eth0`.
2. Sử dụng lệnh `ip` để thêm địa chỉ IPv6 cho giao diện đó. Ví dụ, để thêm địa chỉ IPv6 `2001:db8::1/64` cho giao diện `eth0`, bạn có thể sử dụng lệnh sau:
    
    ```
    sudo ip addr add 2001:db8::1/64 dev eth0
    
    ```
    
    Trong đó, `2001:db8::1/64` là địa chỉ IPv6 bạn muốn thêm và `eth0` là tên của giao diện.
    
3. Sau khi thêm địa chỉ IPv6, bạn có thể sử dụng lệnh `ip addr show` để kiểm tra xem địa chỉ đã được thêm thành công hay chưa.

**Chỉnh sửa tệp cấu hình mạng**:

1. Sử dụng trình soạn thảo văn bản (ví dụ: `sudo nano /etc/network/interfaces`) để mở tệp cấu hình mạng của hệ thống. Tùy theo phiên bản của Linux, tệp cấu hình mạng có thể nằm ở vị trí khác nhau.
2. Tìm đến dòng cấu hình giao diện mà bạn muốn thêm địa chỉ IPv6. Ví dụ:
    
    ```
    iface eth0 inet6 static
    
    ```
    
3. Tiếp theo, thêm dòng sau để đặt địa chỉ IPv6 cho giao diện:
    
    ```
    address 2001:db8::1
    netmask 64
    
    ```
    
    Ở đây, `2001:db8::1` là địa chỉ IPv6 và `64` là độ dài tiền tố mạng (subnet prefix length).
    
4. Lưu tệp cấu hình và thoát khỏi trình soạn thảo.
5. Để áp dụng thay đổi, bạn có thể khởi động lại giao diện mạng hoặc toàn bộ hệ thống.

Sau khi thực hiện các bước trên, địa chỉ IPv6 sẽ được thêm vào giao diện mạng bạn đã chọn.