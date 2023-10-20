# What is swap and what is it used for?

Swap là một phân vùng trên ổ cứng hoặc ổ SSD được sử dụng bởi hệ điều hành để mở rộng bộ nhớ ảo của máy tính. Swap space cung cấp một phần bộ nhớ ảo bổ sung cho bộ nhớ RAM chính (physical RAM) của máy tính. Khi bộ nhớ RAM đã đầy, hệ điều hành sẽ sử dụng swap space để lưu trữ dữ liệu và chương trình tạm thời, giúp tránh tình trạng gây ra lỗi Out of Memory (OOM) và tiếp tục hoạt động.

Các trường hợp sử dụng swap space bao gồm:

1. **Giảm tình trạng thiếu bộ nhớ (Memory Shortage):** Khi bộ nhớ RAM đã sử dụng hết và cần thêm bộ nhớ để lưu trữ dữ liệu và chương trình tạm thời, hệ điều hành sẽ sử dụng swap space để đảm bảo rằng máy tính không bị treo hoặc gặp lỗi.
2. **Hỗ trợ Hibernate (Suspend to Disk):** Trong một số trường hợp, swap space cần thiết để hỗ trợ tính năng "Hibernate" (ngủ đông). Khi bạn đóng máy tính và chọn hibernate, toàn bộ trạng thái của hệ thống sẽ được lưu trữ trên swap space để máy tính có thể khôi phục lại trạng thái đó khi khởi động lại.
3. **Tạo không gian cho dữ liệu tạm thời:** Swap space cũng có thể được sử dụng để lưu trữ các tệp tạm thời hoặc dữ liệu đệm, giúp giảm tải lên bộ nhớ RAM.

Tuy swap space rất hữu ích để đảm bảo tính ổn định của hệ thống và tránh tình trạng bị treo khi bộ nhớ RAM bị thiếu, nhưng việc sử dụng nó cũng có thể dẫn đến giảm hiệu suất do truy cập đĩa cứng, vì đĩa cứng thường chậm hơn RAM. Do đó, quản lý cấu hình swap space cần phải cân nhắc và tối ưu hóa để đảm bảo hiệu suất tốt cho hệ thống.