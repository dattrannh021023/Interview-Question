# Can you have several HTTPS virtual hosts sharing the same IP?

Có, bạn có thể có nhiều ảo hóa HTTPS (HTTPS virtual hosts) chia sẻ cùng một địa chỉ IP trên một máy chủ web. Điều này được gọi là "Server Name Indication" (SNI). SNI là một phần mở rộng của giao thức TLS/SSL, cho phép máy chủ web xác định trang web cụ thể mà khách hàng đang cố gắng truy cập dựa trên tên miền (domain name) được yêu cầu.

Trước khi có SNI, máy chủ HTTPS chỉ có thể phân biệt các trang web bằng cách sử dụng địa chỉ IP và cổng. Điều này đồng nghĩa rằng bạn cần một địa chỉ IP riêng biệt cho mỗi trang web HTTPS bạn muốn cài đặt. Tuy nhiên, với SNI, bạn có thể sử dụng cùng một địa chỉ IP cho nhiều trang web và máy chủ web sẽ xác định trang web cụ thể dựa trên tên miền trong giao thức SSL/TLS handshake.

Điều này rất hữu ích trong trường hợp bạn có một máy chủ vật lý hoặc máy chủ ảo duy nhất và bạn muốn chạy nhiều trang web HTTPS khác nhau trên cùng một địa chỉ IP. Tuy nhiên, cần phải lưu ý rằng không tất cả các trình duyệt và máy chủ hỗ trợ SNI, vì vậy bạn nên kiểm tra tính tương thích của trình duyệt và máy chủ web của mình trước khi triển khai.