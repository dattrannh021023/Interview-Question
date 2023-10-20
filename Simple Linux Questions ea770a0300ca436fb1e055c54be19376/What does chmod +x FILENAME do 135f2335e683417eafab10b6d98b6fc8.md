# What does chmod +x FILENAME do?

Lệnh `chmod +x FILENAME` được sử dụng để thêm quyền thực thi (execute) cho một tệp tin hoặc script trên hệ thống Unix/Linux. Cụ thể, nó cho phép bạn cấp quyền thực thi cho người dùng có quyền sở hữu (owner) của tệp tin đó.

- `chmod`: Là lệnh để thay đổi quyền truy cập tệp tin hoặc thư mục.
- `+x`: Ký tự `+` đại diện cho việc thêm quyền, và `x` đại diện cho quyền thực thi.
- `FILENAME`: Là tên của tệp tin mà bạn muốn thêm quyền thực thi.

Khi bạn chạy lệnh `chmod +x FILENAME`, bạn đang cho phép người dùng có quyền sở hữu (owner) của tệp tin có quyền thực thi nó. Sau khi thực hiện lệnh này, người dùng có thể chạy tệp tin bằng cách sử dụng tên tệp và ./ trước nó (ví dụ: `./FILENAME`), với điều kiện tệp tin đó cũng có quyền đọc.

Lưu ý rằng bạn cần phải có quyền sửa đổi quyền truy cập của tệp tin đó hoặc phải là người sở hữu hoặc có quyền sudo để chạy lệnh `chmod`.