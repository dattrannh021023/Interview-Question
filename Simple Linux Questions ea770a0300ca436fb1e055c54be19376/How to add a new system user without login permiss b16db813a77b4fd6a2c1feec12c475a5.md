# How to add a new system user without login permissions?

Để thêm một người dùng hệ thống mới mà không cấp quyền đăng nhập (login permissions), bạn có thể sử dụng lệnh `useradd` trên hệ thống Unix/Linux. Dưới đây là cách thực hiện điều đó:

```bash
sudo useradd -r username

```

Trong đó:

- `sudo`: Bạn cần có quyền sudo hoặc là root để thực hiện lệnh này.
- `useradd`: Là lệnh để thêm một người dùng hệ thống mới.
- `r`: Tùy chọn này tạo ra một người dùng hệ thống "system user" hoặc "system account," không có quyền đăng nhập. Người dùng này thường được sử dụng để chạy dịch vụ hoặc ứng dụng cụ thể mà không cần đăng nhập.
- `username`: Thay thế bằng tên người dùng mới mà bạn muốn thêm vào hệ thống.

Sau khi thực hiện lệnh này, một người dùng hệ thống mới sẽ được tạo ra, nhưng họ sẽ không có quyền đăng nhập vào hệ thống bằng cách sử dụng tên người dùng này. Thay vào đó, họ thường được sử dụng để chạy các tiến trình hoặc dịch vụ cụ thể mà không cần đăng nhập.