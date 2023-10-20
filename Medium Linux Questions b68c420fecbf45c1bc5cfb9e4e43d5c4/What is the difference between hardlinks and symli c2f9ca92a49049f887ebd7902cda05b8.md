# What is the difference between hardlinks and symlinks? What happens when you remove the source to a symlink/hardlink?

Hard links và symbolic links (symlinks) là hai cách để tạo liên kết đến tệp (file) trong hệ thống Unix/Linux, nhưng chúng có sự khác biệt quan trọng về cách hoạt động và tác động khi bạn xóa nguồn gốc của liên kết.

**Hard Links:**

1. Hard links là một cơ chế trong hệ thống tệp Unix/Linux cho phép bạn tạo nhiều tên (đường dẫn) khác nhau trỏ đến cùng một vùng dữ liệu trên đĩa cứng.
2. Hard links chỉ hoạt động cho các tệp đã tồn tại trên hệ thống tệp và không thể tạo liên kết tới thư mục.
3. Khi bạn xóa một hard link, vùng dữ liệu trên đĩa cứng không bị xóa cho đến khi không còn liên kết nào trỏ đến nó. Dữ liệu vẫn còn tồn tại cho các liên kết khác.

**Symbolic Links (Symlinks):**

1. Symlinks (symbolic links) là một loại liên kết đặc biệt trong hệ thống tệp Unix/Linux, chúng không trỏ trực tiếp đến dữ liệu của tệp mục tiêu mà chỉ chứa đường dẫn đến tệp mục tiêu.
2. Symlinks có thể tạo liên kết đến tệp hoặc thư mục.
3. Khi bạn xóa một symlink, nó không ảnh hưởng đến dữ liệu của tệp mục tiêu. Tệp mục tiêu không bị xóa và các symlinks khác vẫn có thể trỏ đến nó.

Ví dụ:

- Nếu bạn có một tệp `file1.txt` và tạo một hard link `file2.txt` đến nó, khi bạn xóa `file1.txt`, `file2.txt` vẫn tồn tại và trỏ đến cùng vùng dữ liệu.
- Nếu bạn có một tệp `file1.txt` và tạo một symlink `file2.txt` đến nó, khi bạn xóa `file1.txt`, `file2.txt` trở thành "hỏng" (broken) và không thể truy cập dữ liệu mục tiêu (nếu `file1.txt` là mục tiêu).

Tóm lại, sự khác biệt chính giữa hard links và symlinks nằm ở cách chúng trỏ đến dữ liệu mục tiêu và cách chúng hoạt động khi nguồn gốc bị xóa. Hard links trỏ trực tiếp đến dữ liệu, trong khi symlinks chỉ trỏ đến đường dẫn đến dữ liệu mục tiêu.