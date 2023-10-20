# What command will show the available disk space on the Unix/Linux system?

Để hiển thị thông tin về không gian đĩa trống trên hệ thống Unix/Linux, bạn có thể sử dụng lệnh `df` (disk free). Dưới đây là cách sử dụng lệnh `df`:

```bash
df -h

```

Trong đó:

- `h`: Tùy chọn này cho phép hiển thị thông tin về không gian đĩa dưới dạng "human-readable," tức là nó sẽ hiển thị kích thước với các đơn vị như kilobyte (K), megabyte (M), gigabyte (G), v.v., để dễ đọc hơn.

Kết quả sẽ liệt kê tất cả các phân vùng đĩa và không gian trống trên mỗi phân vùng, cùng với thông tin về kích thước tổng cộng, không gian đã sử dụng và không gian trống.

Lệnh `df` là một công cụ hữu ích để kiểm tra tình trạng không gian đĩa trên hệ thống và đảm bảo rằng không gian đĩa không bị đầy đủ, đặc biệt là trên các máy chủ hoặc hệ thống sản xuất.