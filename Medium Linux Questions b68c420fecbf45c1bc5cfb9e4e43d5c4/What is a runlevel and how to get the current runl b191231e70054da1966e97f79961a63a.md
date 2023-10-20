# What is a runlevel and how to get the current runlevel?

Trong hệ thống Unix và Linux, runlevel là một trạng thái hoạt động của hệ thống, xác định các dịch vụ và chế độ làm việc được khởi động hoặc tắt khi hệ thống được khởi động. Mỗi runlevel đại diện cho một trạng thái cụ thể của hệ thống, và nó có thể khác nhau giữa các bản phân phối Linux khác nhau. Một số runlevel thường gặp trong hệ thống Linux bao gồm:

- Runlevel 0: Tắt hệ thống (shutdown).
- Runlevel 1 hoặc S: Chế độ đơn người dùng (single-user mode) hoặc chế độ khẩn cấp (emergency mode).
- Runlevel 2: Chế độ đa người dùng không có dịch vụ NFS.
- Runlevel 3: Chế độ đa người dùng với dịch vụ NFS.
- Runlevel 4: Không được sử dụng thường xuyên.
- Runlevel 5: Chế độ đa người dùng với giao diện đồ họa (GUI).
- Runlevel 6: Khởi động lại hệ thống.

Để xem runlevel hiện tại của hệ thống, bạn có thể sử dụng lệnh `runlevel`. Mở terminal và chạy lệnh sau:

```
runlevel

```

Lệnh này sẽ trả về thông tin về runlevel hiện tại của hệ thống, ví dụ:

```
N 5

```

Trong đó, "N" là runlevel trước khi khởi động lại (có thể là trạng thái hiện tại trước khi bạn thực hiện lệnh khởi động lại), và "5" là runlevel mục tiêu sau khi khởi động lại (chế độ đa người dùng với giao diện đồ họa trong trường hợp này).