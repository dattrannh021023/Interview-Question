# What does & disown after a command do?

Khi bạn sử dụng `& disown` sau một lệnh trong Unix/Linux, nó thực hiện hai công việc:

1. **`&`:** Dấu `&` sau một lệnh khiến lệnh đó chạy trong chế độ nền, giống như khi chỉ sử dụng dấu `&` độc lập. Điều này cho phép lệnh chạy trong nền mà không chặn terminal, và bạn có thể tiếp tục làm việc với terminal mà không cần phải đợi cho lệnh kết thúc.
2. **`disown`:** Lệnh `disown` được sử dụng để gỡ bỏ kết nối giữa lệnh chạy trong nền và terminal. Nó có nghĩa là sau khi bạn sử dụng `disown`, lệnh đó sẽ không bị ảnh hưởng khi bạn đóng hoặc tắt terminal. Nó sẽ tiếp tục chạy ngay cả khi terminal đã đóng.

Kết hợp cả hai, `& disown` thường được sử dụng để bắt đầu một tác vụ trong nền và đảm bảo rằng nó sẽ tiếp tục chạy ngay cả khi bạn đóng terminal. Điều này thường hữu ích khi bạn muốn chạy một dịch vụ hoặc tiến trình dài hạn mà không muốn bị ảnh hưởng bởi việc đóng terminal hoặc mất kết nối với nó.

Ví dụ:

```bash
$ long_running_command &
$ disown

```

Trong ví dụ này, `long_running_command` sẽ chạy trong nền và không bị ảnh hưởng khi bạn đóng terminal.