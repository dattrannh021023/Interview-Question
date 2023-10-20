# Describe briefly the steps you need to follow in order to create a simple master/slave cluster.

Để tạo một cụm (cluster) master/slave đơn giản trong MySQL, bạn có thể tuân theo các bước sau:

1. **Cài đặt MySQL**: Đảm bảo rằng bạn đã cài đặt MySQL trên tất cả các máy chủ mà bạn muốn thêm vào cụm. Bạn cần thiết lập một máy chủ làm master và ít nhất một máy chủ làm slave.
2. **Cấu hình Master Server**:
    - Trong tệp cấu hình MySQL (thường là `/etc/mysql/my.cnf`), bạn cần đảm bảo rằng tham số `server-id` đã được đặt và có một giá trị duy nhất cho máy chủ master.
    - Bật ghi log chuẩn bằng cách đặt `log_bin` thành tên tệp ghi log. Điều này sẽ lưu trữ các sự thay đổi dữ liệu vào một tệp ghi log để máy chủ slave có thể sao chép.
3. **Cấu hình Slave Server**:
    - Trong tệp cấu hình MySQL, đặt `server-id` với giá trị duy nhất khác với máy chủ master.
    - Đặt `replicate-do-db` nếu bạn chỉ muốn sao chép cơ sở dữ liệu cụ thể hoặc `replicate-wild-do-table` nếu bạn chỉ muốn sao chép một số bảng cụ thể.
4. **Khởi động lại Master Server**: Sau khi cấu hình, khởi động lại máy chủ master để áp dụng các thay đổi.
5. **Tạo Tài Khoản Sao Chép Cho Slave**: Trên máy chủ master, tạo một tài khoản MySQL cho việc sao chép và cấp quyền cần thiết.
6. **Sao Chép Dữ Liệu**: Trên máy chủ slave, sử dụng lệnh `CHANGE MASTER TO` để thiết lập máy chủ slave để sao chép từ máy chủ master. Cung cấp thông tin về tên máy chủ master, tên người dùng sao chép và mật khẩu.
7. **Bắt đầu Sao Chép**: Khi cấu hình máy chủ slave hoàn tất, bạn có thể bắt đầu quá trình sao chép bằng cách chạy `START SLAVE`.
8. **Kiểm tra Sao Chép**: Theo dõi các tệp ghi log và tiến trình sao chép trên máy chủ slave để đảm bảo rằng dữ liệu được sao chép thành công từ máy chủ master.
9. **Thiết lập Cơ Bản**: Đảm bảo rằng máy chủ slave đã được cấu hình đúng và hoạt động ổn định.

Lưu ý rằng đây chỉ là một hướng dẫn đơn giản và việc triển khai một cụm master/slave có thể phức tạp hơn trong môi trường thực tế. Ngoài ra, có nhiều cấu hình và tùy chọn khác có thể áp dụng tùy theo yêu cầu cụ thể của bạn.