# Why should you run "mysql_secure_installation" after installing MySQL?

Khi bạn cài đặt MySQL, việc chạy lệnh "mysql_secure_installation" là một bước quan trọng để bảo mật và cấu hình MySQL đúng cách. Dưới đây là lý do tại sao bạn nên chạy lệnh này:

1. **Đặt Mật Khẩu Cho Người Dùng Gốc (Root)**: Lệnh này cho phép bạn đặt mật khẩu cho tài khoản người dùng gốc (root) trong MySQL. Điều này là quan trọng để đảm bảo rằng chỉ những người dùng được ủy quyền mới có thể truy cập và quản lý cơ sở dữ liệu.
2. **Xóa Các Tài Khoản Không Sử Dụng**: "mysql_secure_installation" sẽ xóa bỏ các tài khoản không cần thiết hoặc không an toàn mà MySQL có thể tự động tạo ra trong quá trình cài đặt. Điều này giúp giảm nguy cơ bảo mật bằng cách loại bỏ các tài khoản không cần thiết.
3. **Xóa Bỏ Các Cơ Sở Dữ Liệu Mẫu**: MySQL thường cài đặt một số cơ sở dữ liệu mẫu (ví dụ: test, employees) mà không cần thiết trong môi trường sản xuất. "mysql_secure_installation" sẽ hỏi bạn xem có muốn xóa các cơ sở dữ liệu này hay không.
4. **Tắt Truy Cập Xa Cho Người Dùng Gốc**: Mặc định, tài khoản người dùng gốc có thể truy cập từ xa. Lệnh này sẽ tắt tính năng này nếu bạn không cần thiết phải truy cập MySQL từ xa.
5. **Bật Bộ Kiểm Tra Mật Khẩu Mạnh**: Lệnh "mysql_secure_installation" cũng sẽ bật bộ kiểm tra mật khẩu mạnh cho các tài khoản người dùng MySQL, đảm bảo rằng các mật khẩu được sử dụng là đủ mạnh để chống lại các cuộc tấn công dò mật khẩu.

Tóm lại, chạy "mysql_secure_installation" là một phần quan trọng của việc cài đặt MySQL để đảm bảo rằng hệ thống cơ sở dữ liệu của bạn được cấu hình an toàn và bảo mật.