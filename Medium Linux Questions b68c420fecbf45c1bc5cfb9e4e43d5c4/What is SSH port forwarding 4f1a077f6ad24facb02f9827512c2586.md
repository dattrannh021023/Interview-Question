# What is SSH port forwarding?

SSH port forwarding, còn được gọi là SSH tunneling, là một tính năng của giao thức SSH (Secure Shell) cho phép bạn tạo các kênh mạng an toàn qua một kết nối SSH. Tính năng này cho phép bạn truyền dữ liệu an toàn giữa máy tính cục bộ và máy chủ từ xa thông qua một kết nối SSH, và nó có nhiều ứng dụng hữu ích, bao gồm:

1. **Port Forwarding (Chuyển tiếp cổng):** SSH port forwarding cho phép bạn chuyển tiếp các kết nối từ một cổng trên máy tính cục bộ đến một cổng trên máy chủ từ xa hoặc ngược lại. Có hai loại port forwarding chính:
    - **Local Port Forwarding (Chuyển tiếp cổng cục bộ):** Điều này cho phép bạn chuyển tiếp các kết nối từ máy tính cục bộ của bạn đến máy chủ từ xa thông qua kết nối SSH. Ví dụ, bạn có thể kết nối đến một máy chủ từ xa thông qua SSH và chuyển tiếp kết nối đến cổng MySQL trên máy chủ từ xa để truy cập cơ sở dữ liệu từ máy tính cục bộ của bạn.
    - **Remote Port Forwarding (Chuyển tiếp cổng từ xa):** Điều này cho phép bạn chuyển tiếp các kết nối từ máy tính từ xa đến máy tính cục bộ của bạn thông qua kết nối SSH. Ví dụ, bạn có thể mở một cổng trên máy tính từ xa và chuyển tiếp kết nối đến cổng đó từ máy tính cục bộ của bạn.
2. **Dynamic Port Forwarding (Chuyển tiếp cổng động):** Đây là một tính năng mạnh mẽ của SSH cho phép bạn tạo một máy chủ proxy SOCKS động trên máy tính cục bộ của bạn. Bạn có thể sử dụng máy chủ proxy này để duyệt web hoặc kết nối đến các dịch vụ từ xa thông qua giao thức SOCKS qua kết nối SSH. Điều này giúp bạn bảo vệ dữ liệu và duyệt web một cách an toàn khi kết nối đến mạng từ xa.

Tóm lại, SSH port forwarding là một công cụ mạnh mẽ cho việc tạo các kênh mạng an toàn qua kết nối SSH, cho phép bạn truyền dữ liệu an toàn và truy cập các dịch vụ từ xa một cách an toàn và bảo mật.