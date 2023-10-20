# Describe how 'ps' works.

Lệnh `ps` trong hệ thống Unix và Linux là một công cụ mạnh mẽ để hiển thị thông tin về các tiến trình đang chạy trên hệ thống. Nó là viết tắt của "process status." `ps` hoạt động bằng cách truy vấn và hiển thị thông tin từ bảng dữ liệu của hạt nhân (kernel) về các tiến trình.

Dưới đây là cách `ps` hoạt động:

1. **Thu thập thông tin từ hạt nhân (kernel):** `ps` truy vấn thông tin về các tiến trình từ bảng dữ liệu của hạt nhân. Hạt nhân duy trì thông tin chi tiết về tất cả các tiến trình đang chạy trên hệ thống, bao gồm ID của tiến trình (PID), ID của cha của tiến trình (PPID), trạng thái của tiến trình, ưu tiên thực thi (nice value), bộ nhớ sử dụng, và nhiều thông tin khác.
2. **Lọc và hiển thị thông tin:** Sau khi truy vấn thông tin từ hạt nhân, `ps` lọc thông tin này dựa trên các tùy chọn và tham số mà bạn cung cấp. Bạn có thể sử dụng các tùy chọn khác nhau để chỉ định loại thông tin bạn muốn hiển thị và cách bạn muốn sắp xếp danh sách tiến trình.
3. **Hiển thị kết quả:** Cuối cùng, `ps` hiển thị thông tin được lọc và sắp xếp dưới dạng danh sách các tiến trình trên màn hình của bạn. Kết quả này bao gồm thông tin như PID, TTY (terminal), STAT (trạng thái), TIME (thời gian CPU đã sử dụng), và nhiều thông tin khác.

Cách bạn sử dụng `ps` phụ thuộc vào các tùy chọn và tham số bạn cung cấp. Ví dụ, để liệt kê tất cả các tiến trình đang chạy trên hệ thống, bạn có thể sử dụng lệnh `ps aux`. Để xem danh sách các tiến trình theo dạng cây, bạn có thể sử dụng `ps aux --forest`.

`ps` là một công cụ quan trọng trong quản lý tiến trình trên hệ thống Unix và Linux và được sử dụng rộng rãi để xem, theo dõi, và quản lý tiến trình.