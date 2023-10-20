# What is a Linux kernel module?

Một Linux kernel module (hoặc đơn giản là "kernel module") là một phần mềm mở rộng có khả năng được tải vào hoặc gỡ bỏ từ kernel của hệ điều hành Linux trong thời gian chạy (runtime). Các module này có khả năng mở rộng chức năng của kernel mà không cần phải tải lại hoàn toàn hệ điều hành.

Dưới đây là một số điểm quan trọng về Linux kernel modules:

1. **Chức Năng Bổ Sung:** Kernel modules được sử dụng để thêm chức năng mới vào kernel hoặc mở rộng chức năng hiện có. Điều này cho phép hệ điều hành Linux hỗ trợ nhiều loại phần cứng, giao thức mạng, và tính năng khác mà không cần phải biên dịch lại toàn bộ kernel.
2. **Tải Và Gỡ Bỏ Trong Thời Gian Chạy:** Modules có thể được tải vào hoặc gỡ bỏ từ kernel trong quá trình hệ thống đang chạy mà không cần phải khởi động lại máy tính. Điều này giúp tránh sự gián đoạn của dịch vụ và ứng dụng trong quá trình cập nhật hoặc cài đặt thêm tính năng.
3. **Chia Sẻ Tài Nguyên Kernel:** Modules có thể chia sẻ tài nguyên kernel như mô-đun thiết bị (device driver), hệ thống tệp (filesystem), hoặc các chức năng hạt nhân (kernel functions).
4. **Quản Lý Bởi Hệ Thống Và Người Dùng:** Kernel modules có thể được quản lý bằng cách sử dụng các lệnh như `insmod` (để tải module), `rmmod` (để gỡ bỏ module), và `lsmod` (để liệt kê các module đã tải). Hệ thống tự động quản lý việc tải module trong một số trường hợp, chẳng hạn như khi phát hiện phần cứng mới.
5. **Mã Nguồn Mở:** Nhiều kernel module được phát triển và phân phối với mã nguồn mở, cho phép cộng đồng thay đổi và tùy chỉnh chúng theo nhu cầu cụ thể.

Kernel modules là một phần quan trọng của hệ điều hành Linux, cho phép nó linh hoạt và có khả năng tương thích với nhiều loại phần cứng và yêu cầu ứng dụng khác nhau.