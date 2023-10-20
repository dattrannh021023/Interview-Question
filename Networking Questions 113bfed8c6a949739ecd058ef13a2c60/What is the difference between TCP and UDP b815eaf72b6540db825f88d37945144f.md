# What is the difference between TCP and UDP?

TCP (Transmission Control Protocol) và UDP (User Datagram Protocol) là hai trong những giao thức chính được sử dụng trong mạng máy tính để truyền dữ liệu giữa các thiết bị. Dưới đây là sự khác nhau chính giữa TCP và UDP:

1. **Kết nối và Đáng Tin Cậy**:
    - **TCP**: TCP tạo ra một kết nối logic giữa máy nguồn và đích trước khi truyền dữ liệu. Nó đảm bảo truyền dữ liệu một cách đáng tin cậy, đảm bảo rằng các gói dữ liệu sẽ đến đích và sẽ được xử lý theo đúng thứ tự. Nếu có lỗi, nó sẽ cố gắng sửa chữa hoặc gửi lại dữ liệu.
    - **UDP**: UDP không thiết lập kết nối trước và không đảm bảo tính đáng tin cậy. Nó truyền dữ liệu dưới dạng các gói độc lập. Không có sự kiểm tra lỗi hoặc tái truyền nếu gói dữ liệu bị mất hoặc hỏng.
2. **Độ Trễ**:
    - **TCP**: Do quá trình thiết lập kết nối và kiểm tra đáng tin cậy, TCP thường có độ trễ cao hơn so với UDP. Điều này làm cho nó thích hợp cho các ứng dụng yêu cầu tính đáng tin cậy như trình duyệt web và truyền tệp.
    - **UDP**: UDP có độ trễ thấp hơn do không cần thiết lập kết nối và kiểm tra đáng tin cậy. Điều này làm cho nó thích hợp cho các ứng dụng thời gian thực như trò chơi trực tuyến và streaming media.
3. **Đặc Điểm Ứng Dụng**:
    - **TCP**: Thường được sử dụng cho các ứng dụng cần độ tin cậy và xác định thời gian như email, trình duyệt web, và tải tệp.
    - **UDP**: Thích hợp cho các ứng dụng yêu cầu thời gian thực và không quan trọng về tính đáng tin cậy như VoIP, video streaming, và trò chơi trực tuyến.
4. **Header Size**:
    - **TCP**: TCP header lớn hơn UDP header do chứa nhiều thông tin kiểm tra đáng tin cậy hơn.
    - **UDP**: UDP header nhẹ và hiệu suất hơn trong việc truyền dữ liệu với header nhỏ.
5. **Mục Đích Sử Dụng**:
    - **TCP**: Sử dụng khi cần đảm bảo tính đáng tin cậy và kiểm tra lỗi, ngay cả khi có độ trễ cao hơn.
    - **UDP**: Sử dụng khi cần thời gian thực và độ trễ thấp hơn quan trọng hơn tính đáng tin cậy.

Tùy thuộc vào loại ứng dụng và yêu cầu cụ thể, người quản trị hệ thống sẽ chọn sử dụng TCP hoặc UDP cho việc truyền dữ liệu trên mạng.