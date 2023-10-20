# What is LUKS? How to use it?

LUKS (Linux Unified Key Setup) là một tiêu chuẩn mã hóa đối với việc mã hóa các phân vùng đĩa trên hệ điều hành Linux. Nó cung cấp khả năng bảo mật dữ liệu bằng cách sử dụng mã hóa đối xứng với các phương thức tiêu chuẩn như AES (Advanced Encryption Standard).

Cách sử dụng LUKS để mã hóa một phân vùng đĩa:

1. **Cài đặt LUKS**: Đảm bảo rằng bạn đã cài đặt các gói cần thiết, chẳng hạn như `cryptsetup`. Sử dụng trình quản lý gói của hệ thống để cài đặt nếu chưa có.
2. **Tạo phân vùng**: Trước hết, bạn cần tạo một phân vùng trên đĩa cần mã hóa. Điều này có thể thực hiện bằng cách sử dụng các công cụ như `fdisk` hoặc `parted`.
3. **Mã hóa phân vùng**: Sử dụng lệnh `cryptsetup` để mã hóa phân vùng. Ví dụ, để mã hóa phân vùng `/dev/sdb1` với tên gọi là "myencryptedvolume," bạn có thể thực hiện:
    
    ```bash
    sudo cryptsetup luksFormat /dev/sdb1
    
    ```
    
    Bạn sẽ được yêu cầu nhập mật khẩu. Mật khẩu này sẽ được sử dụng để mở khóa phân vùng sau này.
    
4. **Mở và kích hoạt phân vùng đã mã hóa**: Sử dụng lệnh sau để mở phân vùng đã mã hóa:
    
    ```bash
    sudo cryptsetup luksOpen /dev/sdb1 myencryptedvolume
    
    ```
    
    Bạn sẽ được yêu cầu nhập mật khẩu mà bạn đã thiết lập trước đó.
    
5. **Tạo hệ thống tệp**: Bây giờ bạn đã mở phân vùng đã mã hóa, bạn có thể tạo các hệ thống tệp trên đó, chẳng hạn như một hệ thống tệp EXT4 hoặc XFS.
6. **Sử dụng phân vùng đã mã hóa**: Khi bạn muốn sử dụng phân vùng đã mã hóa, bạn cần mở nó trước bằng lệnh:
    
    ```bash
    sudo cryptsetup luksOpen /dev/sdb1 myencryptedvolume
    
    ```
    
    Sau đó, bạn có thể truy cập phân vùng đã mã hóa thông qua đường dẫn như bất kỳ phân vùng thường thấy khác.
    
7. **Đóng phân vùng đã mã hóa**: Khi bạn đã hoàn thành việc sử dụng phân vùng đã mã hóa, hãy đóng nó để đảm bảo an toàn:
    
    ```bash
    sudo cryptsetup luksClose myencryptedvolume
    
    ```
    

LUKS là một công cụ quan trọng cho việc bảo mật dữ liệu trên Linux và được sử dụng rộng rãi để bảo vệ dữ liệu trên các thiết bị lưu trữ.