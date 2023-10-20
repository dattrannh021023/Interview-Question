# What is the sticky bit?

Bit dính (sticky bit) là một trong các quyền đặc biệt trong hệ thống Unix và Linux. Nó được áp dụng cho các thư mục (directories) và có tác dụng quyết định ai có quyền xóa (delete) các tệp (files) hoặc thư mục bên trong thư mục đó. Bit dính thường được đặt trên thư mục /tmp để đảm bảo tính bảo mật và tránh việc xóa tệp của người dùng khác.

Cụ thể, các điểm quan trọng về bit dính là:

1. **Xóa Tệp trong Thư Mục (Delete Files in Directory):** Khi bit dính được đặt cho một thư mục, người dùng chỉ có thể xóa tệp mà họ tạo ra trong thư mục đó. Người dùng không thể xóa các tệp do người khác tạo ra trong cùng thư mục này, trừ khi họ có quyền ghi (write permission) vào thư mục.
2. **Đặt Bit Dính:** Để đặt bit dính cho một thư mục, bạn có thể sử dụng lệnh `chmod` với tùy chọn "+t" hoặc "+1000". Ví dụ:
    
    ```
    chmod +t /path/to/directory
    
    ```
    
    Lệnh trên sẽ đặt bit dính cho thư mục /path/to/directory.
    
3. **Hiện Thị Bit Dính:** Để kiểm tra xem bit dính có được đặt cho một thư mục hay không, bạn có thể sử dụng lệnh `ls` với tùy chọn "-l" để xem quyền truy cập của thư mục. Nếu bit dính được đặt, bạn sẽ thấy ký tự "t" được hiển thị ở cuối quyền truy cập của thư mục. Ví dụ:
    
    ```
    drwxrwxrwt 2 user1 user1 4096 Oct  9 10:00 example_directory
    
    ```
    
    Trong ví dụ trên, bit dính đã được đặt cho thư mục "example_directory."
    
4. **Ứng Dụng Thường Thấy:** Bit dính thường được sử dụng cho các thư mục chứa tệp tạm thời hoặc các thư mục mà nhiều người dùng có quyền truy cập, như /tmp để đảm bảo tính toàn vẹn và bảo mật dữ liệu.

Bit dính là một cơ chế quan trọng trong hệ thống Unix/Linux để đảm bảo tính toàn vẹn và an toàn của dữ liệu trong các môi trường đa người dùng.