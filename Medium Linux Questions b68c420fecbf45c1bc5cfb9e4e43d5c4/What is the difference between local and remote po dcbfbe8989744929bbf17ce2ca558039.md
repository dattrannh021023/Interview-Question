# What is the difference between local and remote port forwarding?

Local và remote port forwarding là hai loại chuyển tiếp cổng trong SSH, và chúng có các sự khác biệt cơ bản về cách hoạt động và mục tiêu của chúng:

**Local Port Forwarding (Chuyển tiếp cổng cục bộ):**

1. **Hoạt động:** Khi bạn sử dụng local port forwarding, bạn chuyển tiếp các kết nối từ máy tính cục bộ của bạn đến máy chủ từ xa thông qua kết nối SSH.
2. **Mục tiêu:** Mục tiêu của local port forwarding là máy chủ từ xa. Bạn có thể truy cập các dịch vụ hoặc port trên máy chủ từ xa thông qua cổng cục bộ trên máy tính của bạn.
3. **Ví dụ:** Nếu bạn muốn truy cập cơ sở dữ liệu MySQL trên máy chủ từ xa từ máy tính cục bộ của bạn, bạn có thể sử dụng local port forwarding để chuyển tiếp kết nối từ cổng cục bộ (ví dụ: cổng 3306) đến cổng MySQL trên máy chủ từ xa thông qua kết nối SSH.

**Remote Port Forwarding (Chuyển tiếp cổng từ xa):**

1. **Hoạt động:** Khi bạn sử dụng remote port forwarding, bạn chuyển tiếp các kết nối từ máy tính từ xa đến máy tính cục bộ của bạn thông qua kết nối SSH.
2. **Mục tiêu:** Mục tiêu của remote port forwarding là máy tính cục bộ của bạn. Bạn có thể truyền các kết nối từ máy tính từ xa đến cổng cục bộ trên máy tính của bạn.
3. **Ví dụ:** Nếu bạn muốn chuyển tiếp kết nối đến cổng web (ví dụ: cổng 80) trên máy tính từ xa đến máy tính cục bộ của bạn để kiểm tra trang web từ xa, bạn có thể sử dụng remote port forwarding để chuyển tiếp kết nối đến cổng 80 trên máy tính từ xa đến máy tính cục bộ của bạn thông qua kết nối SSH.

Tóm lại, local port forwarding chuyển tiếp từ máy tính cục bộ đến máy chủ từ xa, trong khi remote port forwarding chuyển tiếp từ máy tính từ xa đến máy tính cục bộ. Cả hai loại chuyển tiếp cổng này đều có thể hữu ích trong việc truy cập và quản lý các dịch vụ từ xa thông qua kết nối SSH.