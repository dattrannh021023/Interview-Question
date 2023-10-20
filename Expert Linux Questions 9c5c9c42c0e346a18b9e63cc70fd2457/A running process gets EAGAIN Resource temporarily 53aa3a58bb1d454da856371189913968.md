# A running process gets EAGAIN: Resource temporarily unavailable on reading a socket. How can you close this bad socket/file descriptor without killing the process?

Khi một tiến trình đang chạy gặp lỗi EAGAIN ("Resource temporarily unavailable") khi đọc một socket hoặc file descriptor, bạn có thể thử đóng socket hoặc file descriptor đó mà không cần phải giết tiến trình. Để làm điều này, bạn có thể sử dụng lệnh `lsof` (list open files) và lệnh `kill`.

Dưới đây là các bước thực hiện:

1. Sử dụng lệnh `lsof` để tìm danh sách các file descriptor mà tiến trình đang sử dụng:
    
    ```
    lsof -p <PID>
    
    ```
    
    Trong đó, `<PID>` là ID của tiến trình đang gặp lỗi EAGAIN.
    
2. Lệnh `lsof` sẽ liệt kê tất cả các file descriptor đang mở bởi tiến trình với `<PID>`. Tìm file descriptor mà bạn muốn đóng.
3. Sử dụng lệnh `kill` để gửi một tín hiệu đóng file descriptor đó cho tiến trình. Sử dụng tùy chọn `<signal>` với `kill` để thực hiện điều này. Ví dụ:
    
    ```
    kill -<signal> <PID>
    
    ```
    
    Trong đó, `<signal>` là tín hiệu bạn muốn gửi (thông thường là `9` cho tín hiệu SIGKILL để đóng file descriptor một cách cứng, hoặc `15` cho SIGTERM để yêu cầu tiến trình đóng sạch các file descriptor).
    

Lưu ý rằng việc đóng file descriptor của một tiến trình có thể gây ra tình trạng không ổn định nếu tiến trình không xử lý nó đúng cách. Hãy thực hiện điều này một cách cẩn thận và theo sự chỉ đạo của quản trị hệ thống hoặc người quản lý ứng dụng.