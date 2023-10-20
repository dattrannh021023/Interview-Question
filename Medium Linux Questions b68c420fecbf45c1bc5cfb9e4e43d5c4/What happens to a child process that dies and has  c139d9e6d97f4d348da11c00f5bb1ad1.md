# What happens to a child process that dies and has no parent process to wait for it and what’s bad about this?

Khi một tiến trình con (child process) chết (kết thúc) và không có tiến trình cha (parent process) nào để chờ đợi nó, tiến trình con trở thành một "tiến trình zombie" (zombie process). Tiến trình zombie là một trạng thái trung gian giữa việc tiến trình con kết thúc và việc thông báo cho tiến trình cha rằng tiến trình con đã kết thúc.

Dưới đây là một số điểm quan trọng về tiến trình zombie và tại sao chúng không tốt:

1. **Không tiêu thụ tài nguyên hệ thống:** Tiến trình zombie không tiêu thụ CPU hoặc bộ nhớ hệ thống. Chúng chỉ tồn tại trong bảng dữ liệu của hạt nhân (kernel) để tiến trình cha sau này có thể truy vấn thông tin về tiến trình con.
2. **Dung lượng PID bị lãng phí:** Mỗi tiến trình zombie vẫn giữ một số PID (Process ID) trong bảng dữ liệu hạt nhân. Điều này có nghĩa rằng dung lượng PID bị lãng phí và không thể được sử dụng cho các tiến trình khác.
3. **Quản lý tiến trình không hiệu quả:** Nếu hệ thống có quá nhiều tiến trình zombie, điều này có thể làm cho quản lý tiến trình trở nên không hiệu quả. Dung lượng bảng dữ liệu hạt nhân bị chiếm bởi các tiến trình zombie có thể giảm khả năng quản lý tiến trình hiện hữu.

Để giải quyết vấn đề về tiến trình zombie, tiến trình cha (parent process) cần gọi một hàm gọi là "wait" hoặc "waitpid" để kiểm tra trạng thái của các tiến trình con. Khi tiến trình cha chờ đợi tiến trình con và nhận được thông báo rằng tiến trình con đã kết thúc, tiến trình con sẽ được xóa khỏi bảng dữ liệu hạt nhân và không còn là zombie nữa.

Nếu tiến trình cha không chờ đợi tiến trình con hoặc nếu tiến trình cha đã chết mà không kết thúc đúng cách, các tiến trình zombie có thể tích tụ và gây ra vấn đề về quản lý tiến trình trên hệ thống. Do đó, quá trình quản lý tiến trình và sử dụng hàm "wait" hoặc "waitpid" là quan trọng để tránh tiến trình zombie trên hệ thống.