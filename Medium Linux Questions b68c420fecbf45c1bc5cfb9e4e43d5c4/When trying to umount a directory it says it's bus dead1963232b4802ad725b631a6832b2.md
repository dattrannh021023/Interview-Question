# When trying to umount a directory it says it's busy, how to find out which PID holds the directory?

Khi bạn gặp thông báo rằng một thư mục đóng gói (umount) không thể thực hiện được vì nó đang được sử dụng, bạn có thể sử dụng các lệnh sau để xác định tiến trình (PID) nào đang sử dụng thư mục đó:

1. Sử dụng lệnh `lsof` (list open files) để liệt kê các tệp và thư mục đang được sử dụng bởi các tiến trình:
    
    ```
    sudo lsof +D /đường/dẫn/thư/mục
    
    ```
    
    Thay `/đường/dẫn/thư/mục` bằng đường dẫn tới thư mục bạn muốn kiểm tra. Lệnh này sẽ hiển thị danh sách các tiến trình và tệp mà tiến trình đó đang sử dụng.
    
2. Sử dụng lệnh `fuser` để tìm PID của tiến trình đang sử dụng thư mục:
    
    ```
    sudo fuser -m /đường/dẫn/thư/mục
    
    ```
    
    Lệnh này cũng sẽ cho bạn danh sách các PID của các tiến trình đang sử dụng thư mục.
    
3. Nếu bạn đã xác định PID của tiến trình và muốn tắt nó để có thể umount thư mục, bạn có thể sử dụng lệnh `kill` để kết thúc tiến trình:
    
    ```
    sudo kill -9 PID
    
    ```
    
    Trong đó, `PID` là số tiến trình bạn muốn tắt. Hãy chắc chắn rằng bạn đã sao lưu dữ liệu quan trọng trước khi tắt tiến trình bằng lệnh `kill -9`, vì nó có thể gây mất dữ liệu nếu không được sử dụng đúng cách.
    

Sau khi tắt tiến trình đang sử dụng thư mục, bạn có thể thực hiện lệnh umount để tháo gỡ thư mục đó.