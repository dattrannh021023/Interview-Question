# Explain how could you ssh login into a Linux system that DROPs all new incoming packets using a SSH tunnel.

Để SSH vào một hệ thống Linux mà đã cấu hình để loại bỏ (DROP) tất cả các gói tin đến, bạn có thể sử dụng một SSH tunnel để thiết lập kết nối an toàn.

Dưới đây là các bước để thực hiện điều này:

1. **Tạo một SSH tunnel từ máy cục bộ của bạn đến máy chủ từ xa**:
    
    ```
    ssh -L 2222:localhost:22 username@remote_server
    
    ```
    
    - `L 2222:localhost:22`: Điều này tạo một SSH tunnel trên máy cục bộ của bạn, kết nối cổng 2222 trên máy cục bộ với cổng 22 (SSH) trên máy chủ từ xa. Bạn có thể thay đổi số cổng nếu cần thiết.
2. **Sau khi SSH tunnel đã được thiết lập, sử dụng một phiên SSH mới để kết nối vào máy chủ từ xa thông qua tunnel**:
    
    ```
    ssh -p 2222 localhost
    
    ```
    
    - `p 2222`: Sử dụng cổng 2222, là cổng đã được định tuyến thông qua tunnel trên máy cục bộ của bạn.

Bằng cách này, bạn đã tạo ra một SSH tunnel từ máy cục bộ đến máy chủ từ xa và sau đó sử dụng nó để kết nối vào máy chủ từ xa thông qua localhost. Máy chủ từ xa sẽ xem kết nối này như là một kết nối đến từ localhost, nên nó sẽ không bị tác động bởi việc DROP tất cả các gói tin đến từ bên ngoài.