# How do you provide privileges to a user?

Để cung cấp đặc quyền cho một người dùng trong MySQL, bạn có thể sử dụng câu lệnh `GRANT`. Dưới đây là cách cung cấp đặc quyền cho một người dùng:

1. Đăng nhập vào MySQL bằng tài khoản có đặc quyền quản trị viên (thường là tài khoản "root"):
    
    ```bash
    mysql -u root -p
    
    ```
    
    Sau đó, bạn sẽ được nhắc nhập mật khẩu cho tài khoản root.
    
2. Sử dụng câu lệnh `GRANT` để cung cấp đặc quyền cho người dùng. Ví dụ:
    
    ```sql
    GRANT [LOẠI_QUYỀN] ON [TÊN_CSDL].[TÊN_BẢNG] TO 'TÊN_NGUỜI_DÙNG'@'HOST';
    
    ```
    
    - `[LOẠI_QUYỀN]` là quyền mà bạn muốn cung cấp, ví dụ: `SELECT`, `INSERT`, `UPDATE`, `DELETE`, `ALL PRIVILEGES` (tất cả đặc quyền).
    - `[TÊN_CSDL]` là tên cơ sở dữ liệu mà bạn muốn cung cấp quyền truy cập.
    - `[TÊN_BẢNG]` là tên bảng cụ thể (tùy chọn), nếu bạn chỉ muốn cung cấp quyền cho một bảng cụ thể trong cơ sở dữ liệu.
    - `'TÊN_NGUỜI_DÙNG'@'HOST'` là tài khoản người dùng và host mà bạn muốn cung cấp quyền cho. Host có thể là `'localhost'` (chỉ truy cập từ máy chủ cục bộ) hoặc `'%`'` (truy cập từ bất kỳ host nào).
3. Sau khi cung cấp quyền, bạn cần thực hiện câu lệnh `FLUSH PRIVILEGES` để áp dụng các thay đổi:
    
    ```sql
    FLUSH PRIVILEGES;
    
    ```
    
    Câu lệnh này sẽ đảm bảo rằng các thay đổi về đặc quyền được lưu trữ và áp dụng trong MySQL.
    

Lưu ý rằng để cung cấp đặc quyền, bạn cần có quyền quản trị viên hoặc quyền tương tự trong MySQL.