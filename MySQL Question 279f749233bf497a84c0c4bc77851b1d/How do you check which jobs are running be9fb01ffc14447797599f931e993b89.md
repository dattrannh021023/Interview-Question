# How do you check which jobs are running?

Để kiểm tra các công việc (jobs) đang chạy trong MySQL, bạn có thể sử dụng câu lệnh sau bằng cách sử dụng MySQL Command-Line Client hoặc các công cụ quản lý cơ sở dữ liệu như phpMyAdmin:

```sql
SHOW PROCESSLIST;

```

Câu lệnh này sẽ hiển thị danh sách các kết nối và công việc đang chạy trong MySQL. Mỗi dòng trong kết quả đại diện cho một kết nối và công việc đang thực thi. Các cột quan trọng bao gồm:

- **Id**: ID của kết nối.
- **User**: Tên người dùng thực hiện kết nối.
- **Host**: Địa chỉ IP hoặc tên máy chủ của người dùng.
- **db**: Tên cơ sở dữ liệu mà kết nối đang sử dụng (nếu có).
- **Command**: Loại lệnh SQL mà kết nối đang thực thi.
- **Time**: Thời gian thực hiện công việc (theo giây).
- **State**: Trạng thái của công việc, ví dụ: "Executing," "Sending data,"...

Bạn có thể sử dụng câu lệnh này để xem trạng thái của các truy vấn hoặc công việc trong MySQL và quản lý chúng nếu cần thiết.