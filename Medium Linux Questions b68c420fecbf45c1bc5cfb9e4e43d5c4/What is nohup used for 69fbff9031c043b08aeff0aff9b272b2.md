# What is "nohup" used for?

"nohup" là viết tắt của cụm từ "no hang up," và nó là một lệnh trong hệ thống Unix/Linux được sử dụng để thực hiện một công việc (process) mà không bị ảnh hưởng bởi việc ngắt kết nối với terminal và chạy nền (background).

Cụ thể, "nohup" làm cho một công việc tiếp tục chạy ngay cả khi bạn đóng cửa sổ terminal hoặc ngắt kết nối SSH. Điều này hữu ích khi bạn muốn thực hiện một tác vụ dài hạn mà không muốn nó bị dừng khi bạn thoát khỏi terminal.

Cú pháp cơ bản của "nohup" là:

```
nohup command &

```

Trong đó:

- "command" là lệnh hoặc tác vụ bạn muốn chạy.
- "&" đặt ở cuối để chạy lệnh trong nền.

Khi bạn sử dụng "nohup," các dữ liệu đầu ra của lệnh (stdout và stderr) sẽ được gửi vào một tệp gọi là "nohup.out" trong thư mục làm việc hiện tại mà bạn đã gọi lệnh "nohup."

Ví dụ sử dụng "nohup" để chạy một tác vụ dài hạn:

```
nohup ./long_running_script.sh &

```

Sử dụng "nohup" là một cách để đảm bảo rằng một tác vụ sẽ tiếp tục chạy sau khi bạn thoát khỏi terminal hoặc ngắt kết nối SSH, và kết quả của tác vụ sẽ được lưu vào tệp "nohup.out" để kiểm tra sau này.