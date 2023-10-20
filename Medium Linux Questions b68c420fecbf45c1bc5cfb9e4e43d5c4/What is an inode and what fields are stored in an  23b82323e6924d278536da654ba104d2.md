# What is an inode and what fields are stored in an inode?

Inode (index node) là một khái niệm quan trọng trong hệ thống tệp Unix và Linux. Inode là một cấu trúc dữ liệu được sử dụng để lưu trữ thông tin về các tệp (files) và thư mục (directories) trên đĩa cứng. Mỗi tệp và thư mục trên hệ thống tệp Unix/Linux được gắn với một inode duy nhất, được đánh số theo thứ tự tăng dần.

Các trường thông tin quan trọng được lưu trữ trong một inode bao gồm:

1. **File Type (Loại Tệp):** Inode chứa thông tin về loại tệp, có thể là một tệp thường (regular file), thư mục, liên kết (symbolic link), ổ đĩa cứng (block device), hoặc thiết bị ký tự (character device).
2. **File Size (Kích Thước Tệp):** Inode lưu trữ kích thước của tệp.
3. **File Permissions (Quyền Truy Cập):** Inode chứa thông tin về quyền truy cập đối với tệp hoặc thư mục, bao gồm quyền đọc, ghi và thực thi cho người dùng (owner), nhóm (group) và người dùng khác (others).
4. **Ownership (Chủ Sở Hữu):** Inode lưu trữ thông tin về người dùng và nhóm chủ sở hữu của tệp hoặc thư mục.
5. **Timestamps (Dấu Thời Gian):** Inode bao gồm ba dấu thời gian:
    - Atime (access time): Thời gian truy cập cuối cùng đến tệp hoặc thư mục.
    - Mtime (modification time): Thời gian sửa đổi cuối cùng của nội dung tệp hoặc thư mục.
    - Ctime (change time): Thời gian thay đổi cuối cùng của inode (ví dụ: thay đổi quyền truy cập hoặc chủ sở hữu).
6. **Number of Links (Số Lượng Liên Kết):** Inode lưu trữ số lượng liên kết đến tệp hoặc thư mục. Mỗi liên kết (hard link) tới một tệp tạo thêm một tham chiếu tới inode của nó.
7. **Data Blocks (Khối Dữ Liệu):** Inode chứa địa chỉ các khối dữ liệu thực sự trên đĩa cứng nơi nội dung tệp hoặc thư mục được lưu trữ. Một số inode có khối dữ liệu trực tiếp (direct blocks), khối gián tiếp (indirect blocks), và khối gián tiếp kép (double indirect blocks) để lưu trữ dữ liệu.
8. **File System ID (ID Hệ Thống Tệp):** Inode chứa thông tin về hệ thống tệp mà nó thuộc về.
9. **Number (Số Inode):** Mỗi inode có một số inode duy nhất để xác định nó trong hệ thống tệp.

Inode là một phần quan trọng trong hệ thống tệp Unix/Linux, vì nó cho phép hệ thống quản lý tệp và thư mục một cách hiệu quả, theo dõi các thông tin quan trọng về quyền truy cập, quản lý bộ định danh duy nhất cho mỗi tệp và thư mục, và theo dõi cấu trúc dữ liệu trên đĩa cứng.