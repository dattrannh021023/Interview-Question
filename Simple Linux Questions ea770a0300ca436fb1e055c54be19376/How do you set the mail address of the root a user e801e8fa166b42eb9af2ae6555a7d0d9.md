# How do you set the mail address of the root/a user?

Để đặt địa chỉ email cho người dùng root hoặc một người dùng cụ thể trong hệ thống Unix/Linux, bạn có thể sử dụng tệp cấu hình `/etc/aliases` và sau đó sử dụng lệnh `newaliases` để cập nhật cơ sở dữ liệu alias. Dưới đây là các bước chi tiết:

1. Mở tệp cấu hình `/etc/aliases` bằng một trình soạn thảo văn bản như `nano` hoặc `vi`:
    
    ```bash
    sudo nano /etc/aliases
    
    ```
    
2. Trong tệp `/etc/aliases`, bạn có thể thêm dòng sau để đặt địa chỉ email cho root hoặc người dùng cụ thể. Ví dụ, để đặt địa chỉ email cho root, thêm dòng sau:
    
    ```
    root: your_email@example.com
    
    ```
    
    Để đặt địa chỉ email cho một người dùng cụ thể, thay `your_email@example.com` bằng địa chỉ email thực sự và thay `username` bằng tên người dùng.
    
3. Lưu và đóng tệp cấu hình sau khi thực hiện thay đổi.
4. Sau khi bạn đã thay đổi tệp `/etc/aliases`, bạn cần cập nhật cơ sở dữ liệu alias bằng lệnh sau:
    
    ```bash
    sudo newaliases
    
    ```
    
    Lệnh này sẽ cập nhật cơ sở dữ liệu alias và áp dụng thay đổi.
    

Bây giờ, root hoặc người dùng cụ thể sẽ có địa chỉ email được đặt trong tệp cấu hình alias. Khi hệ thống gửi email đến root hoặc người dùng đó, nó sẽ được chuyển đến địa chỉ email bạn đã cấu hình.