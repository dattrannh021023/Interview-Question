# How can you limit process memory usage?

Bạn có thể giới hạn việc sử dụng bộ nhớ của một tiến trình trong hệ thống Linux bằng cách sử dụng các công cụ và cơ chế sau:

1. **cgroups (Control Groups):** Cgroups là một cơ chế quản lý tài nguyên trong Linux, cho phép bạn giới hạn sự tiêu thụ tài nguyên của các tiến trình. Bạn có thể sử dụng cgroups để giới hạn bộ nhớ RAM và swap của một tiến trình cụ thể hoặc một nhóm tiến trình. Điều này có thể được thực hiện bằng cách sử dụng các tiện ích như `systemd-cgtop`, `cgcreate`, `cgexec`, và `cgset`.
2. **ulimit command:** Lệnh `ulimit` cho phép bạn giới hạn tài nguyên được cấp cho một tiến trình trong phiên làm việc hiện tại. Bạn có thể sử dụng `ulimit` để giới hạn bộ nhớ ảo (virtual memory) hoặc bộ nhớ RSS (Resident Set Size) của một tiến trình. Hãy kiểm tra tài liệu `man ulimit` để biết thêm chi tiết.
3. **Docker và Docker Compose:** Nếu bạn đang chạy tiến trình trong môi trường Docker, bạn có thể sử dụng tùy chọn `-memory` và `-memory-swap` để giới hạn bộ nhớ cho container Docker cụ thể.
4. **Swapiness:** Bạn có thể điều chỉnh cấu hình swapiness trong hệ thống để kiểm soát việc sử dụng swap space (bộ nhớ trang) của hệ thống. Swapiness được sử dụng để quyết định mức độ ưa thích sử dụng swap space thay vì bộ nhớ RAM. Bằng cách tinh chỉnh giá trị swapiness, bạn có thể kiểm soát việc sử dụng swap trong hệ thống.
5. **Các cơ chế trong ứng dụng:** Một số ứng dụng cho phép bạn thiết lập giới hạn bộ nhớ cho chính tiến trình của họ bằng cách sử dụng tùy chọn hoặc tệp cấu hình riêng. Ví dụ, trong Node.js, bạn có thể sử dụng `-max-old-space-size` để giới hạn bộ nhớ.

Lưu ý rằng việc giới hạn bộ nhớ có thể ảnh hưởng đến hoạt động của tiến trình và ứng dụng. Bạn nên xác định cẩn thận mức giới hạn phù hợp để đảm bảo tính ổn định và hiệu suất của hệ thống.