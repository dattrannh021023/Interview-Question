# How do you create a user?

Để tạo một người dùng (user) trong MySQL, bạn có thể sử dụng câu lệnh SQL `CREATE USER`. Dưới đây là cách thực hiện:

1. Đăng nhập vào MySQL bằng tài khoản có đặc quyền quản trị viên (thường là tài khoản "root"):
    
    ```
    mysql -u root -p
    
    ```
    
    Sau đó, bạn sẽ được nhắc nhập mật khẩu cho tài khoản root.
    
2. Sử dụng câu lệnh `CREATE USER` để tạo một người dùng mới. Ví dụ:
    
    ```
    CREATE USER 'ten_nguoi_dung'@'localhost' IDENTIFIED BY 'mat_khau';
    
    ```
    
    - `'ten_nguoi_dung'` là tên người dùng mà bạn muốn tạo.
    - `'localhost'` là host mà người dùng có thể đăng nhập vào. Trong trường hợp này, người dùng chỉ có thể đăng nhập từ máy chủ MySQL cục bộ. Nếu bạn muốn cho phép đăng nhập từ bất kỳ host nào, bạn có thể sử dụng `'%'` thay vì `'localhost'`.
    - `'mat_khau'` là mật khẩu cho người dùng.
3. Sau khi tạo người dùng, bạn có thể cấp các đặc quyền cho họ bằng câu lệnh `GRANT`. Ví dụ:
    
    ```
    GRANT ALL PRIVILEGES ON ten_cSDL.* TO 'ten_nguoi_dung'@'localhost';
    
    ```
    
    - `'ten_cSDL'` là tên cơ sở dữ liệu (database) mà bạn muốn người dùng có quyền truy cập. Thay `'ten_cSDL'` bằng tên cơ sở dữ liệu cụ thể.
    - `'ten_nguoi_dung'@'localhost'` là tài khoản người dùng và host mà bạn muốn cấp quyền cho.
4. Cuối cùng, bạn cần thực hiện câu lệnh `FLUSH PRIVILEGES` để áp dụng các thay đổi về đặc quyền:
    
    ```
    FLUSH PRIVILEGES;
    
    ```
    

Khi bạn đã tạo người dùng và cấp quyền thành công, họ có thể đăng nhập vào MySQL và thực hiện các thao tác trên cơ sở dữ liệu được chỉ định.