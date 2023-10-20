# What does an & after a command do?

Dấu `&` sau một lệnh trong một câu lệnh dòng lệnh Unix/Linux hoặc khi chạy một tác vụ từ terminal có ý nghĩa như sau:

1. **Chạy lệnh nền (Background):** Khi bạn thêm dấu `&` sau một lệnh, nó sẽ cho phép lệnh đó chạy trong chế độ nền. Điều này có nghĩa rằng bạn có thể tiếp tục sử dụng terminal hoặc chạy các lệnh khác mà không cần phải chờ cho lệnh hiện tại kết thúc.

Ví dụ:

```bash
$ long_running_command &

```

Trong ví dụ này, `long_running_command` sẽ chạy trong nền và bạn có thể tiếp tục nhập các lệnh khác vào terminal mà không bị chặn.

1. **Trong một tập lệnh script:** Trong tập lệnh script, dấu `&` có thể được sử dụng để bắt đầu một công việc con (subprocess) và cho phép script tiếp tục thực hiện các câu lệnh khác mà không cần phải chờ cho công việc con kết thúc.

Ví dụ:

```bash
#!/bin/bash
echo "Starting a background job"
background_job &
echo "Script continues..."

```

Trong ví dụ trên, `background_job` sẽ được chạy trong nền, và script sẽ tiếp tục thực hiện các câu lệnh sau đó mà không phải đợi cho công việc con kết thúc.

Dấu `&` là một cách hữu ích để làm việc với các tác vụ dài hạn hoặc song song trong môi trường Unix/Linux.