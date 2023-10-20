# How to know which process listens on a specific port?

Để biết tiến trình nào đang lắng nghe trên một cổng cụ thể, bạn có thể sử dụng một số lệnh và công cụ trên Unix và Linux. Dưới đây là một số cách để làm điều đó:

1. **Sử dụng lệnh `netstat`:** Lệnh `netstat` có thể được sử dụng để xem danh sách các kết nối mạng và các cổng đang lắng nghe. Để tìm tiến trình lắng nghe trên một cổng cụ thể, bạn có thể chạy lệnh sau:
    
    ```bash
    netstat -tuln | grep PORT_NUMBER
    
    ```
    
    Thay thế `PORT_NUMBER` bằng số cổng bạn quan tâm. Lệnh này sẽ liệt kê thông tin về cổng và tiến trình đang lắng nghe trên cổng đó.
    
2. **Sử dụng lệnh `ss`:** Lệnh `ss` tương tự như `netstat` và có thể được sử dụng để kiểm tra các kết nối mạng và cổng đang lắng nghe. Dưới đây là một ví dụ:
    
    ```bash
    ss -tuln | grep PORT_NUMBER
    
    ```
    
    Thay thế `PORT_NUMBER` bằng số cổng bạn quan tâm.
    
3. **Sử dụng `lsof` (List Open Files):** `lsof` là một công cụ mạnh mẽ để xem danh sách các tệp và cổng đang được mở bởi tiến trình. Bạn có thể sử dụng nó để xác định tiến trình đang lắng nghe trên một cổng cụ thể bằng cách chạy lệnh sau:
    
    ```bash
    lsof -i :PORT_NUMBER
    
    ```
    
    Thay thế `PORT_NUMBER` bằng số cổng bạn muốn kiểm tra.
    
4. **Sử dụng `ps` và `grep`:** Nếu bạn đã biết rằng một tiến trình cụ thể đang lắng nghe trên cổng, bạn có thể sử dụng `ps` và `grep` để tìm tiến trình đó. Ví dụ:
    
    ```bash
    ps aux | grep PROCESS_NAME
    
    ```
    
    Thay thế `PROCESS_NAME` bằng tên tiến trình bạn đã biết đang lắng nghe trên cổng cụ thể.
    

Nhớ rằng bạn cần có quyền truy cập hệ thống để chạy các lệnh này, đặc biệt là để xem thông tin về các tiến trình khác.