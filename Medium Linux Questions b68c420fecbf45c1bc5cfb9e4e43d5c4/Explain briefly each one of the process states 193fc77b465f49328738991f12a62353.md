# Explain briefly each one of the process states.

Tiến trình (process) trong hệ thống Unix và Linux có thể tồn tại trong một số trạng thái (process states) khác nhau, mỗi trạng thái biểu thị tình trạng của tiến trình tại một thời điểm cụ thể. Dưới đây là các trạng thái quan trọng của tiến trình và giải thích ngắn gọn về mỗi trạng thái:

1. **Running (Chạy):** Tiến trình trong trạng thái Running đang được thực thi trên CPU. Chỉ có một tiến trình có thể chạy trên CPU tại một thời điểm. Tiến trình này có thể chạy hoặc đang chờ đợi thực hiện.
2. **Ready (Sẵn sàng):** Tiến trình trong trạng thái Ready đã sẵn sàng để chạy, nhưng không đủ CPU để thực thi. Chúng có thể đang chờ được lên lịch để chạy sau này.
3. **Blocked (Bị chặn):** Tiến trình trong trạng thái Blocked đang chờ đợi một sự kiện nào đó để xảy ra, chẳng hạn như đọc dữ liệu từ đĩa cứng hoặc đợi một kết nối mạng. Tiến trình trong trạng thái này không thể chạy cho đến khi sự kiện mong muốn xảy ra.
4. **Terminated (Kết thúc):** Tiến trình trong trạng thái Terminated đã kết thúc thực thi và không còn tồn tại. Tuy nhiên, thông tin về tiến trình này vẫn còn trong bảng dữ liệu của hạt nhân để tiến trình cha (parent process) có thể kiểm tra kết quả của tiến trình con.
5. **Zombie (Xác sống):** Tiến trình trong trạng thái Zombie là tiến trình con đã kết thúc, nhưng tiến trình cha của nó chưa kết thúc quá trình chờ đợi (wait) để xác nhận việc kết thúc của nó. Tiến trình zombie là một trạng thái tạm thời và cần được tiến trình cha "cleanup" để giải phóng tài nguyên.
6. **Stopped (Dừng lại):** Tiến trình trong trạng thái Stopped đã bị ngưng lại tạm thời. Điều này có thể do một tín hiệu (signal) hoặc do sự can thiệp của người dùng hoặc hệ thống.

Trạng thái của tiến trình có thể thay đổi theo thời gian, chẳng hạn khi một tiến trình từ trạng thái Running chuyển sang Blocked khi đang đọc dữ liệu từ đĩa cứng. Quản lý tiến trình là một phần quan trọng của hệ điều hành để đảm bảo hiệu suất và sử dụng tài nguyên hiệu quả trên hệ thống.