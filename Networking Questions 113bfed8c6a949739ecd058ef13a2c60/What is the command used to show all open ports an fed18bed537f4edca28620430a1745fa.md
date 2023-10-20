# What is the command used to show all open ports and/or socket connections on a machine?

Câu lệnh được sử dụng để hiển thị tất cả các cổng mạng mở và/hoặc kết nối socket trên một máy tính thường là `netstat`. Để hiển thị tất cả các cổng và kết nối mạng, bạn có thể sử dụng câu lệnh sau:

```
netstat -tuln

```

- `t`: Hiển thị thông tin về các kết nối TCP.
- `u`: Hiển thị thông tin về các kết nối UDP.
- `l`: Chỉ hiển thị các cổng mạng đang lắng nghe (listening).
- `n`: Hiển thị địa chỉ IP và số cổng dưới dạng địa chỉ số (không thực hiện định danh tên miền).

Câu lệnh trên sẽ liệt kê tất cả các cổng mạng mà máy tính đang lắng nghe và tất cả các kết nối mạng hiện tại.

Ngoài `netstat`, bạn cũng có thể sử dụng câu lệnh `ss` để thực hiện công việc tương tự:

```
ss -tuln

```

Cả hai câu lệnh `netstat` và `ss` đều làm việc tương tự và cung cấp thông tin về các cổng mạng và kết nối mạng trên máy tính của bạn.