# How do you change TCP stack buffers? How do you calculate it?

Để thay đổi kích thước các bộ đệm (buffers) của TCP stack trên một hệ thống Linux và tính toán chúng, bạn có thể sử dụng các tham số và công cụ liên quan đến hệ thống. Dưới đây là cách thực hiện:

1. **Xác định các tham số TCP buffer mặc định:** Để xem các giá trị mặc định cho các tham số buffer của TCP stack, bạn có thể sử dụng lệnh `sysctl`. Ví dụ:
    
    ```
    sysctl net.ipv4.tcp_rmem
    sysctl net.ipv4.tcp_wmem
    
    ```
    
    Lệnh này sẽ hiển thị giá trị mặc định của bộ đệm đọc (`tcp_rmem`) và bộ đệm ghi (`tcp_wmem`) cho giao thức TCP trên hệ thống.
    
2. **Thay đổi giá trị buffer:** Để thay đổi kích thước của các buffer, bạn có thể sử dụng lệnh `sysctl` hoặc chỉnh sửa các tệp cấu hình hệ thống. Ví dụ:
    - Sử dụng `sysctl`:
        
        ```
        sysctl -w net.ipv4.tcp_rmem="4096 8192 16384"
        sysctl -w net.ipv4.tcp_wmem="4096 8192 16384"
        
        ```
        
        Trong đó, `"4096 8192 16384"` là giá trị mới cho bộ đệm đọc và bộ đệm ghi. Điều này đặt kích thước bộ đệm tối thiểu, ưu tiên và tối đa.
        
    - Chỉnh sửa tệp `/etc/sysctl.conf` (hoặc các tệp cấu hình tương tự) để áp dụng thay đổi này vĩnh viễn.
3. **Tính toán giá trị buffer:** Để tính toán giá trị buffer phù hợp cho hệ thống của bạn, bạn cần xem xét mục đích sử dụng cụ thể và tài nguyên có sẵn. Một cách tiếp cận thông thường là:
    - Xác định băng thông của liên kết mạng: Bạn cần biết băng thông tối đa của kết nối mạng đến máy chủ.
    - Chia băng thông cho số kết nối cùng lúc: Giả sử bạn có nhiều kết nối cùng lúc, hãy chia băng thông cho số lượng kết nối đó để xác định kích thước buffer cần thiết cho mỗi kết nối.
    - Lưu ý rằng giá trị bộ đệm có thể ảnh hưởng đến hiệu suất và tiêu tốn tài nguyên. Hãy điều chỉnh chúng một cách cẩn thận và theo dõi hiệu suất hệ thống sau khi thay đổi để đảm bảo rằng nó phù hợp với môi trường của bạn.

Lưu ý rằng thay đổi kích thước buffer của TCP stack có thể ảnh hưởng đến hiệu suất của ứng dụng mạng, vì vậy hãy thực hiện thay đổi này cẩn thận và dựa trên nhu cầu cụ thể của hệ thống và ứng dụng của bạn.