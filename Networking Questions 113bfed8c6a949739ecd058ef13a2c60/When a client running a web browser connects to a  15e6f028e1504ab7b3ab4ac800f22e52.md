# When a client running a web browser connects to a web server, what is the source port and what is the destination port of the connection?

Khi một máy khách (client) chạy trình duyệt web kết nối đến một máy chủ web (web server), thì cổng nguồn (source port) của kết nối thường được chọn tự động từ một phạm vi cổng cao và đặt trước (ephemeral ports). Còn cổng đích (destination port) của kết nối thường là cổng 80 cho HTTP hoặc cổng 443 cho HTTPS.

- Cổng 80 là cổng mặc định cho giao thức HTTP, được sử dụng cho các trang web không được mã hóa.
- Cổng 443 là cổng mặc định cho giao thức HTTPS, được sử dụng cho các trang web có kết nối được mã hóa bảo mật.

Nhưng đáng lưu ý rằng, các trình duyệt web hiện đại thường sử dụng cả cổng nguồn và cổng đích động (dynamic ports) để tạo nhiều kết nối đến máy chủ web cùng một lúc để tăng tốc độ tải trang web và hiển thị nhiều tài nguyên đồng thời. Do đó, trong thực tế, cổng nguồn có thể thay đổi đối với mỗi kết nối cụ thể.