# How to add/remove a group from a user?

Để thêm một người dùng vào một nhóm hoặc xóa người dùng khỏi một nhóm trong hệ thống Unix/Linux, bạn có thể sử dụng các lệnh sau đây:

### Thêm một người dùng vào một nhóm:

Để thêm một người dùng vào một nhóm, bạn có thể sử dụng lệnh `usermod` hoặc `gpasswd`, tùy thuộc vào phiên bản hệ thống và tùy chọn mà bạn thích.

### Sử dụng `usermod`:

```bash
sudo usermod -a -G groupname username

```

Trong đó:

- `sudo`: Bạn cần có quyền sudo hoặc là root để thực hiện lệnh này.
- `usermod`: Là lệnh để sửa đổi thông tin người dùng.
- `a`: Tùy chọn này cho biết bạn muốn thêm người dùng vào nhóm, không phải thay đổi nhóm mặc định của họ.
- `G groupname`: Điều này chỉ định tên của nhóm bạn muốn thêm người dùng vào.
- `username`: Tên của người dùng bạn muốn thêm vào nhóm.

### Sử dụng `gpasswd`:

```bash
sudo gpasswd -a username groupname

```

Trong đó:

- `sudo`: Bạn cần có quyền sudo hoặc là root để thực hiện lệnh này.
- `gpasswd`: Là lệnh để quản lý mật khẩu nhóm và thành viên của nhóm.
- `a`: Tùy chọn này cho biết bạn muốn thêm người dùng vào nhóm.
- `username`: Tên của người dùng bạn muốn thêm vào nhóm.
- `groupname`: Tên của nhóm bạn muốn thêm người dùng vào.

### Xóa một người dùng khỏi một nhóm:

Để xóa một người dùng khỏi một nhóm, bạn có thể sử dụng lệnh `gpasswd`:

```bash
sudo gpasswd -d username groupname

```

Trong đó:

- `sudo`: Bạn cần có quyền sudo hoặc là root để thực hiện lệnh này.
- `gpasswd`: Là lệnh để quản lý mật khẩu nhóm và thành viên của nhóm.
- `d`: Tùy chọn này cho biết bạn muốn xóa người dùng khỏi nhóm.
- `username`: Tên của người dùng bạn muốn xóa khỏi nhóm.
- `groupname`: Tên của nhóm bạn muốn xóa người dùng khỏi.

Lưu ý rằng sau khi thay đổi thành viên của một nhóm, bạn có thể cần đăng xuất và đăng nhập lại hoặc khởi động lại các dịch vụ liên quan để thay đổi có hiệu lực.