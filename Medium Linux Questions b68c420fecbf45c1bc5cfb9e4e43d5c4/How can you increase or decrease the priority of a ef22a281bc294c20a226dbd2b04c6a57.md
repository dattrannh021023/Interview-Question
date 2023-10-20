# How can you increase or decrease the priority of a process in Linux?

Trong Linux, bạn có thể tăng hoặc giảm ưu tiên của một tiến trình bằng cách sử dụng các công cụ và lệnh quản lý tiến trình như `nice`, `renice`, và `ionice`. Dưới đây là cách thực hiện điều này:

1. **Sử dụng lệnh `nice`:**
    - Để tăng ưu tiên của một tiến trình, bạn có thể sử dụng lệnh `nice` với giá trị âm. Ví dụ, để tăng ưu tiên của một tiến trình với ID là `PID` lên mức độ ưu tiên thấp hơn, bạn có thể chạy lệnh sau:
        
        ```
        nice -n <priority> <command>
        
        ```
        
        Trong đó, `<priority>` là giá trị âm để tăng ưu tiên (ví dụ: -10), và `<command>` là lệnh bạn muốn thực thi với ưu tiên đã thay đổi.
        
    - Để giảm ưu tiên của một tiến trình, bạn sử dụng giá trị dương cho `<priority>`.
2. **Sử dụng lệnh `renice`:**
    - Để điều chỉnh ưu tiên của một tiến trình đã tồn tại, bạn có thể sử dụng lệnh `renice`. Ví dụ, để tăng ưu tiên của một tiến trình có PID là `PID` lên mức độ ưu tiên thấp hơn, bạn có thể chạy lệnh sau:
        
        ```
        renice <priority> -p <PID>
        
        ```
        
        Trong đó, `<priority>` là giá trị âm để tăng ưu tiên, và `<PID>` là ID của tiến trình cần điều chỉnh.
        
3. **Sử dụng `ionice` (cho I/O priority):**
    - Để điều chỉnh ưu tiên I/O cho một tiến trình, bạn có thể sử dụng lệnh `ionice`. Điều này quan trọng khi bạn muốn kiểm soát tốc độ đọc và ghi vào đĩa của một tiến trình. Ví dụ, để thực hiện một lệnh với ưu tiên I/O thấp hơn, bạn có thể chạy:
        
        ```
        ionice -c <class> -n <priority> <command>
        
        ```
        
        Trong đó, `<class>` là lớp ưu tiên I/O (0, 1, hoặc 2), `<priority>` là giá trị ưu tiên (1-7), và `<command>` là lệnh bạn muốn thực hiện.
        

Lưu ý rằng để sử dụng các lệnh này, bạn cần có quyền root hoặc quyền sudo. Điều này đảm bảo rằng bạn có khả năng điều chỉnh ưu tiên của các tiến trình mà bạn không tạo ra hoặc không thuộc quyền sở hữu của bạn.