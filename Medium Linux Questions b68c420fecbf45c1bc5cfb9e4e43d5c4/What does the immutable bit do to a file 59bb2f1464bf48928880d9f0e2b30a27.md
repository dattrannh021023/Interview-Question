# What does the immutable bit do to a file?

Bit không thay đổi (immutable bit) là một thuộc tính mà bạn có thể gán cho một tệp (file) trong hệ thống Unix/Linux. Khi tệp có bit không thay đổi được đặt, nó có một số tác động quan trọng đối với việc sửa đổi và xóa tệp. Cụ thể:

1. **Không Thể Sửa Đổi Tệp:** Khi bit không thay đổi được đặt cho một tệp, tệp đó không thể bị sửa đổi hoặc cập nhật bởi bất kỳ ai, bao gồm cả người dùng có quyền ghi (write) vào tệp và cả quản trị hệ thống. Ngay cả người dùng có quyền superuser (root) cũng không thể thay đổi tệp này.
2. **Không Thể Xóa Tệp:** Tương tự, khi bit không thay đổi được đặt cho tệp, tệp đó không thể bị xóa hoặc di chuyển bởi bất kỳ ai, kể cả root. Điều này đảm bảo tính toàn vẹn của tệp trong trường hợp tệp quan trọng hoặc quan trọng.
3. **Bảo Vệ Dữ Liệu Quan Trọng:** Bit không thay đổi thường được sử dụng để bảo vệ các tệp quan trọng hoặc các tệp hệ thống chống việc xóa hoặc sửa đổi nhầm lẫn. Ví dụ, các tệp cấu hình hệ thống, tệp ghi log quan trọng hoặc tệp chứa dữ liệu quan trọng có thể được đánh dấu bằng bit không thay đổi để đảm bảo tính toàn vẹn của chúng.

Để đặt bit không thay đổi cho một tệp, bạn có thể sử dụng lệnh `chattr` trên hệ thống Linux. Để xóa bit không thay đổi, bạn cũng có thể sử dụng `chattr` với tùy chọn "-i."

Lưu ý rằng việc sử dụng bit không thay đổi cần phải thực hiện cẩn thận, vì nó có thể làm cho việc quản lý tệp trở nên khó khăn. Việc quên mật khẩu hoặc cách để thay đổi tệp sau khi đặt bit không thay đổi có thể gây mất dữ liệu.