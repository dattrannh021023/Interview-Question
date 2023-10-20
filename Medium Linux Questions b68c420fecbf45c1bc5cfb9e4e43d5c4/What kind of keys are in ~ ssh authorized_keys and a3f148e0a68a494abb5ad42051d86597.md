# What kind of keys are in ~/.ssh/authorized_keys and what it is this file used for?

Tập tin `~/.ssh/authorized_keys` là một tập tin quan trọng trong hệ thống SSH (Secure Shell) và nó được sử dụng để quản lý việc xác thực và phân quyền truy cập cho các máy chủ từ xa bằng cách sử dụng SSH. Tập tin này chứa danh sách các khóa công khai (public keys) của các người dùng hoặc máy chủ client được phép truy cập máy chủ từ xa mà tập tin này thuộc về. Dưới đây là một số điểm quan trọng về `authorized_keys`:

1. **Loại khóa trong tập tin:** Tập tin `authorized_keys` chứa các khóa công khai (public keys) của người dùng hoặc máy chủ client. Khóa công khai là một phần của cặp khóa SSH (bao gồm cả khóa công khai và khóa riêng tư) và được sử dụng để xác thực người dùng khi họ cố gắng kết nối đến máy chủ từ xa bằng SSH.
2. **Xác thực:** Khi một người dùng hoặc máy chủ client cố gắng kết nối đến máy chủ SSH, máy chủ sẽ kiểm tra xem khóa công khai của họ có trùng khớp với bất kỳ khóa nào trong tập tin `authorized_keys` không. Nếu có sự trùng khớp, họ sẽ được xác thực và cho phép truy cập.
3. **Phân quyền:** Tập tin `authorized_keys` không chỉ xác thực người dùng mà còn quản lý quyền truy cập của họ. Bạn có thể đặt quyền cụ thể (ví dụ: cho phép hoặc từ chối truy cập vào máy chủ) cho từng khóa công khai trong tập tin này.
4. **Độ bảo mật:** Chỉ những người dùng có khóa công khai nằm trong tập tin `authorized_keys` được xác thực và truy cập máy chủ từ xa. Điều này giúp đảm bảo tính bảo mật của hệ thống SSH.

Để thêm khóa công khai của một người dùng hoặc máy chủ client vào tập tin `authorized_keys`, bạn có thể sao chép nội dung của khóa công khai vào tập tin này. Mỗi khóa nên được đặt trên một dòng riêng biệt. Sau khi chỉnh sửa tập tin `authorized_keys`, bạn cần đảm bảo rằng tập tin này có đủ quyền truy cập cho người dùng và không cho phép việc chỉnh sửa từ xa.

Tập tin `~/.ssh/authorized_keys` chủ yếu được sử dụng để quản lý xác thực và phân quyền truy cập thông qua SSH và là một phần quan trọng của việc bảo mật hệ thống từ xa.