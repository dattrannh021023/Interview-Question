# What are the steps to add a user to a system without using useradd/adduser?

Để thêm một người dùng vào hệ thống mà không sử dụng lệnh `useradd` hoặc `adduser`, bạn có thể thực hiện các bước sau bằng cách thay đổi các tệp và thư mục hệ thống thủ công:

1. **Tạo Thư mục Home cho Người Dùng:**
Trước tiên, bạn cần tạo một thư mục home cho người dùng mới. Thư mục này sẽ là nơi người dùng lưu trữ các tệp và thư mục cá nhân của họ. Thường, thư mục home được đặt trong `/home`, và bạn có thể tạo nó bằng lệnh sau (thay thế "username" bằng tên người dùng bạn muốn thêm):
    
    ```bash
    sudo mkdir /home/username
    
    ```
    
2. **Tạo Người Dùng Trong `/etc/passwd`:**
Bây giờ, bạn cần thêm thông tin của người dùng vào tệp `/etc/passwd`, một tệp chứa thông tin về các người dùng trên hệ thống. Bạn có thể sử dụng lệnh sau để thêm một dòng cho người dùng (thay thế "username" bằng tên người dùng và "userid" bằng ID người dùng):
    
    ```bash
    sudo echo "username:x:userid:groupid:User description:/home/username:/bin/bash" >> /etc/passwd
    
    ```
    
    - "username": Tên người dùng mới.
    - "x": Trường mật khẩu, thông thường được thiết lập thành "x" để sử dụng mật khẩu băm.
    - "userid": ID người dùng mới (phải là một số không trùng lặp với người dùng khác).
    - "groupid": ID nhóm cho người dùng (thông thường tương tự với userid).
    - "User description": Mô tả ngắn gọn về người dùng.
    - "/home/username": Đường dẫn đến thư mục home mà bạn đã tạo ở bước trước.
    - "/bin/bash": Đường dẫn đến shell mặc định của người dùng (thường là `/bin/bash` cho hầu hết các người dùng).
3. **Tạo Thư Mục Home Mặc Định cho Người Dùng:**
Bạn cần sao chép các tệp và thư mục mẫu từ `/etc/skel` vào thư mục home của người dùng:
    
    ```bash
    sudo cp -r /etc/skel/. /home/username/
    
    ```
    
    Điều này sẽ tạo các tệp và thư mục mẫu (như `.bashrc`, `.profile`, vv.) trong thư mục home của người dùng.
    
4. **Thiết Lập Mật Khẩu Cho Người Dùng (Tùy chọn):**
Bạn có thể sử dụng lệnh `passwd` để thiết lập mật khẩu cho người dùng:
    
    ```bash
    sudo passwd username
    
    ```
    
    Lệnh này sẽ yêu cầu bạn nhập mật khẩu mới cho người dùng.
    
5. **Phân quyền thư mục home (Tùy chọn):**
Đảm bảo thư mục home của người dùng có quyền truy cập đúng:
    
    ```bash
    sudo chown -R username:username /home/username
    
    ```
    
    Thay thế "username" bằng tên người dùng.
    
6. **Đăng nhập Như Người Dùng Mới (Tùy chọn):**
Bạn có thể đăng nhập như người dùng mới bằng lệnh `su` hoặc `sudo su` để kiểm tra tài khoản và đảm bảo mọi thứ hoạt động như mong đợi.

Nhớ thay thế "username," "userid," và "groupid" bằng giá trị thực tế bạn muốn sử dụng cho người dùng mới. Lưu ý rằng việc thêm người dùng thủ công có thể phức tạp hơn và đòi hỏi quyền quản trị viên hệ thống.