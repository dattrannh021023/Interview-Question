# How to force/trigger a file system check on next reboot?

Để bắt buộc hoặc kích hoạt kiểm tra hệ thống tệp (file system check) cho một ổ đĩa tại lần khởi động kế tiếp trong hệ thống Unix/Linux, bạn có thể sử dụng lệnh `touch` để tạo một tệp đặc biệt được gọi là "forcefsck" trong thư mục gốc của ổ đĩa.

Dưới đây là các bước thực hiện:

1. Mở terminal.
2. Đăng nhập với quyền superuser (root) hoặc sử dụng lệnh `sudo` để thực hiện các lệnh sau.
3. Sử dụng lệnh `touch` để tạo tệp "forcefsck" trong thư mục gốc của ổ đĩa bạn muốn kiểm tra. Thường, ổ đĩa gốc là `/`, nhưng nếu bạn muốn kiểm tra một phân vùng cụ thể, hãy chỉ định đường dẫn của phân vùng đó. Ví dụ:
    
    ```
    sudo touch /forcefsck
    
    ```
    
4. Sau khi bạn đã tạo tệp "forcefsck," hệ thống sẽ kiểm tra hệ thống tệp của ổ đĩa đó khi khởi động lần tiếp theo.
5. Khởi động lại máy tính của bạn bằng cách sử dụng lệnh `reboot` hoặc `shutdown -r now` để kích hoạt kiểm tra hệ thống tệp.

Khi hệ thống khởi động lại, kiểm tra hệ thống tệp (fsck) sẽ tự động chạy trên ổ đĩa bạn đã tạo tệp "forcefsck." Hệ thống sẽ xem xét và sửa chữa các vấn đề liên quan đến hệ thống tệp trong trường hợp có lỗi. Sau khi kiểm tra hoàn tất, máy tính sẽ tiếp tục khởi động bình thường.