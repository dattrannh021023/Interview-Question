# How can you tell if the httpd package was already installed?

Để kiểm tra xem gói `httpd` (máy chủ web Apache) đã được cài đặt trên hệ thống Linux của bạn hay chưa, bạn có thể sử dụng một số lệnh kiểm tra tùy thuộc vào hệ thống quản lý gói mà bạn đang sử dụng. Dưới đây là một số ví dụ cho các hệ thống quản lý gói phổ biến:

1. **Trên CentOS/RHEL (sử dụng YUM):**
    
    ```
    yum list installed | grep httpd
    
    ```
    
    Lệnh này sẽ liệt kê tất cả các gói đã được cài đặt trên hệ thống và sử dụng `grep` để tìm kiếm gói `httpd`.
    
2. **Trên Ubuntu/Debian (sử dụng APT):**
    
    ```
    dpkg -l | grep apache2
    
    ```
    
    Hoặc:
    
    ```
    dpkg-query -l | grep apache2
    
    ```
    
    Cả hai lệnh trên đều kiểm tra các gói đã được cài đặt và sử dụng `grep` để tìm kiếm gói Apache.
    
3. **Trên hệ thống sử dụng dnf (Fedora, CentOS 8 trở lên):**
    
    ```
    dnf list installed httpd
    
    ```
    
    Lệnh này sẽ liệt kê các gói đã được cài đặt trên hệ thống và tìm kiếm gói `httpd`.
    

Nếu gói `httpd` đã được cài đặt, bạn sẽ thấy một danh sách các phiên bản và gói phụ thuộc liên quan đến `httpd`. Nếu không có kết quả trả về, điều đó có nghĩa là gói `httpd` chưa được cài đặt trên hệ thống của bạn.