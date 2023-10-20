# How can you list the contents of a package?

Để liệt kê nội dung của một gói cài đặt trên hệ thống Linux, bạn có thể sử dụng các lệnh liên quan đến hệ thống quản lý gói của bạn. Dưới đây là một số ví dụ cho các hệ thống quản lý gói phổ biến:

1. **Trên CentOS/RHEL (sử dụng YUM):**
    
    Để liệt kê nội dung của gói, bạn có thể sử dụng lệnh `yum list` kết hợp với tùy chọn `files`:
    
    ```
    yum list files package-name
    
    ```
    
    Ví dụ, để liệt kê nội dung của gói `httpd`, bạn có thể chạy lệnh sau:
    
    ```
    yum list files httpd
    
    ```
    
2. **Trên Ubuntu/Debian (sử dụng APT):**
    
    Để liệt kê nội dung của gói, bạn có thể sử dụng lệnh `dpkg -L`:
    
    ```
    dpkg -L package-name
    
    ```
    
    Ví dụ, để liệt kê nội dung của gói `apache2`, bạn có thể chạy lệnh sau:
    
    ```
    dpkg -L apache2
    
    ```
    
3. **Trên hệ thống sử dụng dnf (Fedora, CentOS 8 trở lên):**
    
    Để liệt kê nội dung của gói, bạn có thể sử dụng lệnh `dnf repoquery`:
    
    ```
    dnf repoquery -l package-name
    
    ```
    
    Ví dụ, để liệt kê nội dung của gói `httpd`, bạn có thể chạy lệnh sau:
    
    ```
    dnf repoquery -l httpd
    
    ```
    

Lệnh trên sẽ liệt kê tất cả các tệp và thư mục được cài đặt bởi gói trên hệ thống của bạn.