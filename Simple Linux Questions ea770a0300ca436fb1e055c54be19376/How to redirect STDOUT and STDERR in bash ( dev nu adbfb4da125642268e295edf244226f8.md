# How to redirect STDOUT and STDERR in bash? (> /dev/null 2>&1)

Để chuyển hướng đầu ra chuẩn (STDOUT) và đầu ra lỗi chuẩn (STDERR) trong môi trường dòng lệnh Bash, bạn có thể sử dụng cú pháp sau:

```bash
command > /dev/null 2>&1

```

Dưới đây là cách cụ thể hoạt động của cú pháp này:

- `command`: Đây là lệnh mà bạn muốn thực hiện và chuyển hướng đầu ra của nó.
- `>`: Dấu lớn hơn (>) được sử dụng để chuyển hướng đầu ra chuẩn (STDOUT) của lệnh `command`.
- `/dev/null`: Đây là một tệp đặc biệt trên hệ thống Unix/Linux được sử dụng để loại bỏ dữ liệu đầu ra. Bằng cách chuyển hướng đầu ra sang `/dev/null`, bạn buộc lệnh `command` ghi đầu ra của nó vào một "đi vào đâu đó" không thể đọc được.
- `2>&1`: Dùng để chuyển hướng đầu ra lỗi chuẩn (STDERR) của lệnh `command` để nó trùng với đầu ra chuẩn (STDOUT). Cụ thể, nó nghĩa là lỗi chuẩn cũng được ghi vào `/dev/null`, tương tự như đầu ra chuẩn.

Kết quả của cú pháp này là cả đầu ra chuẩn và đầu ra lỗi chuẩn của `command` đều bị gửi đến `/dev/null`, nghĩa là chúng sẽ bị loại bỏ và không xuất hiện trên màn hình hoặc trong tệp tin nào. Điều này thường được sử dụng khi bạn muốn thực hiện một lệnh mà bạn không quan tâm đến đầu ra hoặc bạn muốn ẩn các thông báo lỗi.