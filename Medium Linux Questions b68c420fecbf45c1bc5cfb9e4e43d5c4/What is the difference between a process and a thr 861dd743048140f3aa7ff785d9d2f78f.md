# What is the difference between a process and a thread? And parent and child processes after a fork system call?

**Sự khác biệt giữa tiến trình (process) và luồng (thread):**

1. **Tiến trình (Process):**
    - Một tiến trình là một chương trình hoạt động độc lập trên hệ thống.
    - Mỗi tiến trình có bộ riêng của nó bao gồm không gian địa chỉ, các biến toàn cục, bộ đếm chương trình (program counter), stack, và tài nguyên hệ thống như tệp và socket.
    - Tiến trình tương tác với nhau thông qua cơ chế truyền thông như các ứng dụng gửi dữ liệu qua mạng.
    - Mỗi tiến trình có ít nhất một luồng, được gọi là luồng chính (main thread), và có thể tạo ra thêm các luồng khác để thực hiện công việc cụ thể. Tuy nhiên, các luồng trong cùng một tiến trình chia sẻ cùng một không gian địa chỉ và tài nguyên hệ thống.
2. **Luồng (Thread):**
    - Một luồng là một đơn vị nhỏ hơn của một tiến trình.
    - Các luồng trong cùng một tiến trình chia sẻ cùng một không gian địa chỉ và tài nguyên hệ thống với tiến trình cha và các luồng khác trong tiến trình đó.
    - Luồng thường được sử dụng để thực hiện các công việc đồng thời và cải thiện hiệu suất của một tiến trình bằng cách tận dụng nhiều lõi CPU.

**Sự khác biệt giữa tiến trình cha và tiến trình con sau lệnh hệ thống fork:**

1. **Tiến trình cha (Parent Process):**
    - Tiến trình cha là tiến trình gọi hàm `fork()` để tạo một tiến trình con.
    - Sau khi `fork()` hoàn thành, tiến trình cha và tiến trình con tiếp tục thực hiện song song, bắt đầu từ điểm gọi `fork()`. Điều này có nghĩa rằng cả tiến trình cha và tiến trình con có thể có mã và dữ liệu riêng của họ.
2. **Tiến trình con (Child Process):**
    - Tiến trình con là bản sao của tiến trình cha sau lệnh `fork()`.
    - Tiến trình con bắt đầu thực hiện tại điểm `fork()` và thường được sử dụng để thực hiện các công việc khác nhau so với tiến trình cha.
    - Tiến trình con có cùng mã máy (code) và dữ liệu với tiến trình cha ban đầu, nhưng chúng có một không gian địa chỉ riêng. Các thay đổi trong không gian địa chỉ của tiến trình con không ảnh hưởng đến tiến trình cha và ngược lại.

Tóm lại, tiến trình và luồng là hai khái niệm quan trọng trong việc quản lý và thực hiện đa nhiệm trên hệ thống. Tiến trình cha và tiến trình con sau `fork()` cho phép tạo ra một bản sao của một tiến trình hiện tại, và chúng có không gian địa chỉ và tài nguyên riêng để thực hiện công việc độc lập.