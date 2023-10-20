# Which difference have between public and private SSH key?

The main difference between a public SSH key and a private SSH key is that `the public key is meant to be **shared with others**`, while `the private key is meant to be **kept secret**`.

**Public SSH key**

- Can be shared with anyone who needs to connect to your computer using SSH.
- `Used to **verify** your **identity`** when connecting to a remote server.
- `Cannot` be used to `decrypt` data encrypted with your private key.

**Private SSH key**

- Must be kept secret.
- Used to decrypt data encrypted with your public key.
- Can also be used to sign code or documents digitally.

When you generate a public and private SSH key pair, the two keys are mathematically related, but it is very difficult to calculate the private key from the public key. This is what makes SSH keys so secure.

Here is an example of how SSH keys are used:

1. You generate a public and private SSH key pair.
2. You share your public key with the administrator of a remote server that you want to connect to.
3. When you connect to the remote server using SSH, the server will use your public key to verify your identity.
4. If your identity is verified, the server will allow you to log in.
5. Once you are logged in, you can use your private key to decrypt any data that is encrypted with your public key.

SSH keys are a very secure way to connect to remote servers. They are also very convenient, as you do not need to remember a password for each server that you connect to.

Here are some tips for using SSH keys safely:

- Keep your private key secret. Do not share it with anyone else.
- Store your private key in a secure location. You may want to consider using a password manager to store your private key.
- Use a strong passphrase to protect your private key.
- Change your passphrase regularly.
- Monitor your SSH logs for any suspicious activity.

If you follow these tips, you can help to protect your computer and data from unauthorized access.

SSH (Secure Shell) là một giao thức mạng được sử dụng để thiết lập kết nối an toàn và bảo mật giữa hai máy tính. Trong SSH, có sự khác biệt quan trọng giữa khóa SSH công khai (public SSH key) và khóa SSH riêng tư (private SSH key):

1. **Public SSH Key (Khóa SSH công khai):**
    - Public SSH key là một phần của cặp khóa SSH, và nó được chia sẻ công khai. Nó thường được sao chép và lưu trữ trên máy chủ SSH mà bạn muốn kết nối đến.
    - Public SSH key không bao giờ được giữ bí mật và có thể được chia sẻ an toàn với bất kỳ ai.
    - Khi bạn muốn kết nối đến một máy chủ SSH, bạn cung cấp khóa SSH công khai của mình cho máy chủ. Khóa này được sử dụng để xác minh danh tính của bạn.
2. **Private SSH Key (Khóa SSH riêng tư):**
    - Private SSH key là phần bí mật của cặp khóa SSH. Nó phải được bảo mật một cách cẩn thận và không bao giờ được chia sẻ hoặc tiết lộ.
    - Private SSH key là khóa mà bạn sử dụng để xác minh danh tính của mình và thiết lập kết nối SSH đến các máy chủ. Nó phải được lưu trữ an toàn trên máy tính hoặc thiết bị của bạn.
    - Khi bạn kết nối đến máy chủ SSH, máy tính của bạn sử dụng private SSH key để tạo chữ ký số cho việc xác minh danh tính của bạn.

Sự khác biệt chính giữa khóa SSH công khai và riêng tư là khóa công khai có thể được chia sẻ và lưu trữ một cách công khai, trong khi khóa riêng tư phải được bảo vệ một cách nghiêm ngặt và chỉ có bạn có quyền truy cập vào nó. Cặp khóa SSH công khai và riêng tư làm cho SSH trở thành một giao thức bảo mật mạnh mẽ để thiết lập kết nối an toàn và xác thực trên mạng.