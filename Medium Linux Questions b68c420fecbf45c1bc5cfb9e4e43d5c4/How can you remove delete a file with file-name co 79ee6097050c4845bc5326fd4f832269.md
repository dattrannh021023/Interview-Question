# How can you remove/delete a file with file-name consisting of only non-printable/non-type-able characters?

Để xóa một tệp có tên chứa chỉ các ký tự không in được hoặc không thể nhập từ bàn phím (non-printable/non-type-able characters), bạn có thể sử dụng lệnh `find` kết hợp với lệnh `rm`. Dưới đây là cách bạn có thể thực hiện:

1. Mở terminal trên hệ thống của bạn.
2. Sử dụng lệnh `ls -i` để xem số inode của tệp cần xóa. Ví dụ, nếu số inode của tệp là 12345, bạn sẽ thấy đầu ra như sau:
    
    ```
    12345 filename
    
    ```
    
3. Sử dụng lệnh `find` và số inode để xóa tệp. Sử dụng tùy chọn `inum` để tìm tệp với số inode cụ thể và `exec` để xóa nó. Dưới đây là cú pháp:
    
    ```
    find /path/to/directory -inum 12345 -exec rm -i {} \\;
    
    ```
    
    - `/path/to/directory` là đường dẫn đến thư mục chứa tệp cần xóa.
    - `12345` là số inode của tệp.
    - `exec rm -i {} \\;` sẽ xóa tệp và yêu cầu xác nhận từ bạn trước khi xóa.
4. Khi bạn chạy lệnh trên, nó sẽ tìm và xóa tệp có số inode cụ thể mà bạn đã chỉ định.

Lưu ý rằng bạn cần phải cẩn thận khi sử dụng lệnh `find` và `rm`, và đảm bảo rằng bạn xác định đúng số inode của tệp cần xóa để tránh xóa nhầm tệp quan trọng.