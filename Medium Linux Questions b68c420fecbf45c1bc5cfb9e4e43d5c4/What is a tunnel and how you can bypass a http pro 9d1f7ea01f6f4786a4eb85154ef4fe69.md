# What is a tunnel and how you can bypass a http proxy?

Một "tunnel" (hầm) trong ngữ cảnh mạng máy tính là một kỹ thuật được sử dụng để chuyển tiếp dữ liệu qua một mạng hoặc máy chủ trung gian mà không bị gián đoạn hoặc kiểm soát bởi các yếu tố trung gian. Có hai loại chính của tunneling:

1. **Tunneling Mạng (Network Tunneling):** Kỹ thuật này cho phép bạn tạo một kênh ảo (tunnel) trên mạng để chuyển tiếp dữ liệu qua một mạng công cộng, chẳng hạn như internet, mà không bị kiểm soát bởi các máy chủ trung gian. Một ví dụ phổ biến là sử dụng Virtual Private Network (VPN) để tạo một kênh riêng tư qua internet để bảo vệ dữ liệu khỏi sự kiểm soát và theo dõi.
2. **Tunneling Ứng dụng (Application Tunneling):** Kỹ thuật này cho phép bạn tạo một kênh truyền qua các máy chủ proxy hoặc tường lửa để truy cập các dịch vụ hoặc trang web bị chặn hoặc kiểm soát. Một ví dụ phổ biến là sử dụng SSH tunneling để tạo một kênh bảo mật thông qua máy chủ proxy HTTP để truy cập trang web hoặc dịch vụ trên internet.

Để bypass một HTTP proxy bằng cách sử dụng tunneling ứng dụng, bạn có thể thực hiện các bước sau bằng cách sử dụng SSH tunneling:

1. **Cài đặt một máy chủ SSH trên một máy chủ từ xa (ví dụ: máy chủ cá nhân hoặc máy chủ cloud).**
2. *Sử dụng SSH Client trên máy tính của bạn để tạo một SSH tunnel tới máy chủ từ xa. Sử dụng lệnh sau trong dòng lệnh:
    
    ```
    ssh -D <local_port> <username>@<remote_server>
    
    ```
    
    - `<local_port>` là cổng trên máy tính của bạn mà bạn muốn sử dụng làm cổng gửi yêu cầu qua tunnel.
    - `<username>` là tên người dùng trên máy chủ từ xa.
    - `<remote_server>` là địa chỉ IP hoặc tên miền của máy chủ từ xa.
3. **Cấu hình trình duyệt hoặc các ứng dụng khác để sử dụng SOCKS proxy trên cổng đã chọn (port `<local_port>`).**
4. *Khi bạn truy cập một trang web hoặc dịch vụ, yêu cầu sẽ được gửi qua SSH tunnel và sau đó được gửi đến máy chủ từ xa, giúp bạn truy cập các trang web hoặc dịch vụ mà không bị kiểm soát hoặc chặn bởi proxy HTTP.

Lưu ý rằng việc sử dụng tunneling để bypass proxy có thể vi phạm quy định hoặc chính sách của tổ chức bạn và có thể bị xem xét là một hành vi không đúng đắn. Hãy luôn tuân thủ các quy định và chính sách của tổ chức bạn về việc sử dụng mạng và máy tính.