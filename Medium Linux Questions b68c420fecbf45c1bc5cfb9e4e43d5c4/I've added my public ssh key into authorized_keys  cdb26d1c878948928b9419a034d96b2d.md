# I've added my public ssh key into authorized_keys but I'm still getting a password prompt, what can be wrong?

Nếu bạn đã thêm khóa SSH công khai của mình vào tập tin `authorized_keys` trên máy chủ và vẫn nhận được lời nhắc mật khẩu khi kết nối bằng SSH, có một số nguyên nhân có thể gây ra vấn đề này:

1. **Quyền truy cập tập tin `authorized_keys`:** Đảm bảo rằng tập tin `~/.ssh/authorized_keys` của người dùng trên máy chủ có đủ quyền truy cập. Tập tin này cần được set quyền `600` (rw-------) để đảm bảo tính bảo mật.
    
    ```bash
    chmod 600 ~/.ssh/authorized_keys
    
    ```
    
2. **Quyền truy cập thư mục `~/.ssh`:** Cả thư mục `~/.ssh` chứa tập tin `authorized_keys` cũng cần có quyền truy cập đúng. Thư mục này cần set quyền `700` (rwx------).
    
    ```bash
    chmod 700 ~/.ssh
    
    ```
    
3. **Chính xác khóa công khai:** Đảm bảo rằng bạn đã sao chép đúng khóa công khai của mình vào tập tin `authorized_keys` và không có dấu cắt ngắn hoặc thay đổi nào trong quá trình sao chép.
4. **Định dạng tập tin `authorized_keys`:** Mỗi khóa công khai nên nằm trên một dòng riêng biệt trong tập tin `authorized_keys`. Đảm bảo rằng bạn không đặt cả khóa công khai trên một dòng duy nhất.
5. **Xác thực SSH bằng khóa công khai:** Khi kết nối bằng SSH, hãy đảm bảo rằng bạn đã chọn xác thực bằng khóa công khai thay vì xác thực mật khẩu. Bạn có thể sử dụng tùy chọn `i` để chỉ định khóa riêng tư khi kết nối:
    
    ```bash
    ssh -i /path/to/private_key user@hostname
    
    ```
    
6. **Kiểm tra tên tập tin `authorized_keys`:** Đôi khi, tên tập tin `authorized_keys` trên máy chủ không được viết đúng cách hoặc bị lẫn lộn với tên khác. Hãy đảm bảo bạn đã đặt tên tập tin thành `.ssh/authorized_keys` trong thư mục chính của người dùng.
7. **Khởi động lại dịch vụ SSH:** Thỉnh thoảng, sau khi thay đổi tập tin `authorized_keys`, bạn có thể cần khởi động lại dịch vụ SSH để áp dụng các thay đổi.
    
    ```bash
    sudo service ssh restart
    
    ```
    
8. **Kiểm tra cấu hình SSH:** Đôi khi, cấu hình SSH trên máy chủ có thể cấu hình để yêu cầu cả hai xác thực bằng khóa và mật khẩu. Kiểm tra tệp cấu hình SSH (`/etc/ssh/sshd_config` trên Ubuntu) và đảm bảo rằng tùy chọn `PasswordAuthentication` được đặt thành `no` để tắt xác thực bằng mật khẩu.
    
    ```bash
    PasswordAuthentication no
    
    ```
    
9. **Kiểm tra tường lửa:** Đảm bảo rằng tường lửa trên máy chủ không chặn kết nối SSH. Điều này đặc biệt quan trọng nếu bạn đã thay đổi cổng mặc định của SSH từ 22.
10. **Log lỗi SSH:** Kiểm tra tệp nhật ký SSH trên máy chủ (thường là `/var/log/auth.log` hoặc `/var/log/secure`) để xem nếu có thông báo lỗi cụ thể về vấn đề xác thực.

Nếu sau khi kiểm tra các yếu tố trên mà vẫn gặp vấn đề, bạn n

ên xem xét tìm kiếm hỗ trợ trực tuyến hoặc tư vấn với một chuyên gia hệ thống để tìm giải pháp cụ thể cho tình huống của bạn.