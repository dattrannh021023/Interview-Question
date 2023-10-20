# Explain the three load averages and what do they indicate. What command can be used to view the load averages?

Ba chỉ số tải (load averages) thường được thảo luận trên hệ thống Unix/Linux để đo lường tải của hệ thống và hiệu suất làm việc của nó. Chúng được tính toán trong khoảng thời gian cố định và thường là 1 phút, 5 phút và 15 phút. Các chỉ số này cho biết mức độ sử dụng tài nguyên của hệ thống trong khoảng thời gian cụ thể và có thể được xem bằng lệnh `uptime`.

1. **1-Minute Load Average:** Chỉ số này thể hiện tải trung bình của hệ thống trong vòng 1 phút gần đây. Nó phản ánh mức độ sử dụng tài nguyên và công việc đang xử lý trong khoảng thời gian ngắn hạn. Một con số 1-Minute Load Average lớn hơn 1 có thể chỉ ra hệ thống đang hoạt động ở trạng thái bận rộn và có thể gặp hiện tượng xếp hàng cho các tác vụ.
2. **5-Minute Load Average:** Đây là tải trung bình của hệ thống trong vòng 5 phút gần đây. Chỉ số này cho biết mức độ tải và công việc của hệ thống trong khoảng thời gian trung bình, giúp phát hiện ra sự biến đổi trong tải làm việc.
3. **15-Minute Load Average:** Chỉ số này thể hiện tải trung bình của hệ thống trong vòng 15 phút gần đây. Nó dùng để đánh giá xu hướng tải hệ thống trong khoảng thời gian dài hơn. Nếu 15-Minute Load Average liên tục cao, có thể có vấn đề về tài nguyên hệ thống hoặc hiệu suất yếu.

Lệnh `uptime` được sử dụng để xem ba chỉ số tải này cùng với các thông tin khác về thời gian làm việc của hệ thống và số lượng người dùng đang đăng nhập. Sử dụng lệnh sau để xem load averages:

```bash
uptime

```

Ví dụ về kết quả của lệnh `uptime`:

```
14:32:07 up 7 days, 2:45, 2 users, load average: 0.03, 0.04, 0.00

```

Trong ví dụ này, ba chỉ số tải lần lượt là 0.03, 0.04 và 0.00 cho 1-Minute, 5-Minute và 15-Minute Load Averages. Chúng thấp, cho thấy hệ thống đang hoạt động ở trạng thái nhẹ và có sẵn tài nguyên cho các tác vụ khác.