# What is a zombie process and what could be the cause of it?

Tiến trình zombie là một tiến trình con (child process) đã kết thúc (kết thúc thực thi), nhưng tiến trình cha (parent process) của nó chưa kết thúc quá trình chờ đợi (wait) để xác nhận việc kết thúc của nó. Tiến trình zombie là một trạng thái trung gian giữa việc tiến trình con kết thúc và việc thông báo cho tiến trình cha rằng tiến trình con đã kết thúc.

Nguyên nhân của tiến trình zombie có thể bao gồm:

1. **Tiến trình cha không chờ đợi:** Một trong những nguyên nhân phổ biến nhất của tiến trình zombie là tiến trình cha không gọi hàm "wait" hoặc "waitpid" để kiểm tra trạng thái của tiến trình con sau khi nó kết thúc. Hàm "wait" hoặc "waitpid" là cách tiến trình cha xác nhận kết quả của tiến trình con và giải phóng tài nguyên của nó.
2. **Tiến trình cha bị "đóng cửa" (terminated) trước:** Nếu tiến trình cha kết thúc trước khi tiến trình con hoàn thành, hệ thống không có tiến trình cha để xử lý tiến trình con sau khi nó kết thúc.
3. **Lỗi trong mã của tiến trình cha:** Một lỗi trong mã của tiến trình cha có thể gây ra việc không gọi hàm "wait" hoặc "waitpid" để kiểm tra trạng thái của tiến trình con.

Tiến trình zombie không tiêu thụ tài nguyên hệ thống (CPU hoặc bộ nhớ) và không ảnh hưởng đến hoạt động của hệ thống, nhưng nếu chúng tích tụ quá nhiều, hệ thống có thể trở nên không hiệu quả trong việc quản lý tiến trình. Do đó, quá trình quản lý tiến trình và sử dụng hàm "wait" hoặc "waitpid" để kiểm tra trạng thái của tiến trình con là quan trọng để tránh tiến trình zombie trên hệ thống.