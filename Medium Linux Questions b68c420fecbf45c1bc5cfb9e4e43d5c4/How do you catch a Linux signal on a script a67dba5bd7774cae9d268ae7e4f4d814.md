# How do you catch a Linux signal on a script?

Để bắt một tín hiệu (signal) trong một tập lệnh Linux, bạn có thể sử dụng câu lệnh `trap`. Câu lệnh `trap` cho phép bạn xác định hành động nào sẽ được thực hiện khi tập lệnh nhận được một tín hiệu cụ thể. Dưới đây là cách bạn có thể bắt tín hiệu trong một tập lệnh:

```bash
#!/bin/bash

# Định nghĩa hàm để xử lý tín hiệu
handle_signal() {
    echo "Nhận được tín hiệu $1"
    # Thực hiện xử lý tín hiệu ở đây, ví dụ: dừng tập lệnh hoặc thực hiện một hành động cụ thể.
    # Ví dụ: exit 1
}

# Bắt tín hiệu SIGINT (Ctrl+C) và gọi hàm handle_signal khi nhận được
trap 'handle_signal SIGINT' SIGINT

# Bắt tín hiệu SIGTERM và gọi hàm handle_signal khi nhận được
trap 'handle_signal SIGTERM' SIGTERM

# Bắt tín hiệu khác nếu cần thiết
# trap 'handle_signal TEN_TIN_HIEU' TEN_TIN_HIEU

# Đoạn mã chính của tập lệnh ở đây

# Ví dụ: vòng lặp vô hạn để duy trì tập lệnh hoạt động
while true; do
    sleep 1
done

```

Trong ví dụ trên, tập lệnh sẽ bắt tín hiệu SIGINT (Ctrl+C) và SIGTERM và gọi hàm `handle_signal` để xử lý tín hiệu này. Bạn có thể thay đổi hàm `handle_signal` để thực hiện các hành động cụ thể dựa trên tín hiệu nhận được.

Lưu ý rằng việc xử lý tín hiệu trong một tập lệnh là một phần quan trọng của việc tạo các tập lệnh ổn định và an toàn trên Linux, đặc biệt là trong các trường hợp khi bạn cần thực hiện các tác vụ như giải phóng tài nguyên hoặc lưu trữ dữ liệu trước khi tập lệnh kết thúc.