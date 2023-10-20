# What's happening when the Linux kernel is starting the OOM killer and how does it choose which process to kill first?

Khi hệ thống Linux gặp tình huống kiệt quệ tài nguyên (Out of Memory - OOM), điều quan trọng là phải giải quyết vấn đề này để tránh sự sụp đổ hoặc treo của hệ thống. Trong tình huống này, kernel Linux sẽ kích hoạt một thành phần gọi là OOM Killer (Out Of Memory Killer) để xác định và kết thúc một số tiến trình để giải phóng bộ nhớ và làm cho hệ thống tiếp tục hoạt động.

OOM Killer hoạt động dựa trên một số tiêu chí để chọn tiến trình để kết thúc. Các tiêu chí chính bao gồm:

1. **Score OOM:** Mỗi tiến trình được gán một điểm số OOM dựa trên các yếu tố như sử dụng bộ nhớ hiện tại, sử dụng trang trống và ưu tiên OOM. Tiến trình với điểm số OOM cao hơn có khả năng bị OOM Killer kết thúc trước.
2. **Badness Function:** Kernel sử dụng một hàm "badness" để tính toán điểm số OOM cho mỗi tiến trình. Hàm này ước tính mức độ "xấu" của tiến trình dựa trên các thông tin về sử dụng bộ nhớ và ưu tiên của tiến trình.
3. **Sử dụng Bộ nhớ không thể thay thế:** Tiến trình sử dụng bộ nhớ không thể thay thế (non-swappable) như bộ nhớ kernel hoặc bộ nhớ đã bị khóa sẽ có ưu tiên cao hơn trong việc tránh bị kết thúc.
4. **Lịch sử OOM:** Kernel sẽ xem xét lịch sử OOM trước đó để tránh kết thúc cùng một tiến trình lặp đi lặp lại.
5. **Ưu tiên OOM:** Một số tiến trình được đánh dấu với ưu tiên OOM cao hơn, cho phép họ được ưu tiên trong quyết định kết thúc.
6. **Oom_adj/Oom_score_adj:** Các tiến trình có thể được điều chỉnh bằng cách đặt oom_adj (hoặc oom_score_adj trong phiên bản gần đây hơn) để ảnh hưởng đến điểm số OOM của họ.

Sau khi tính toán điểm số OOM cho tất cả các tiến trình, OOM Killer sẽ chọn tiến trình có điểm số OOM cao nhất để kết thúc. Sau đó, tiến trình này sẽ bị kết thúc và bộ nhớ của nó sẽ được giải phóng để cứu hệ thống khỏi tình trạng kiệt quệ tài nguyên.

Lưu ý rằng việc OOM Killer kết thúc một tiến trình là một biện pháp tương đối cuối cùng và có thể gây ra mất mát dữ liệu hoặc gây ảnh hưởng đến hiệu suất ứng dụng. Do đó, việc tối ưu hóa việc quản lý bộ nhớ và sử dụng các công cụ quản lý tài nguyên là quan trọng để tránh tình huống OOM.