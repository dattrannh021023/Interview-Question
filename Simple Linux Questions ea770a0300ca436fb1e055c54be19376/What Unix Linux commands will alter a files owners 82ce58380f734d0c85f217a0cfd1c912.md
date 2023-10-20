# What Unix/Linux commands will alter a files ownership, files permissions?

Trong Unix/Linux, bạn có thể sử dụng các lệnh sau để thay đổi sở hữu và quyền truy cập của tệp tin hoặc thư mục:

1. **Thay đổi sở hữu tệp tin hoặc thư mục:**
    - `chown`: Lệnh `chown` được sử dụng để thay đổi sở hữu của tệp tin hoặc thư mục. Ví dụ:
        
        ```bash
        chown new_owner:new_group file_or_directory
        
        ```
        
        Trong đó:
        
        - `new_owner`: Tên người dùng mới mà bạn muốn gán sở hữu cho tệp tin hoặc thư mục.
        - `new_group`: Tên nhóm mới mà bạn muốn gán cho tệp tin hoặc thư mục.
        - `file_or_directory`: Tệp tin hoặc thư mục bạn muốn thay đổi sở hữu.
2. **Thay đổi quyền truy cập tệp tin hoặc thư mục:**
    - `chmod`: Lệnh `chmod` được sử dụng để thay đổi quyền truy cập của tệp tin hoặc thư mục. Bạn có thể sử dụng `chmod` với các ký tự hoặc số để đặt quyền truy cập. Ví dụ:
        
        ```bash
        chmod permissions file_or_directory
        
        ```
        
        Trong đó:
        
        - `permissions`: Mã quyền truy cập bạn muốn đặt cho tệp tin hoặc thư mục, có thể sử dụng ký tự hoặc số.
        - `file_or_directory`: Tệp tin hoặc thư mục bạn muốn thay đổi quyền truy cập.
    
    Ví dụ sử dụng ký tự:
    
    ```bash
    chmod u+rwx file_or_directory
    
    ```
    
    Ví dụ sử dụng số (octal):
    
    ```bash
    chmod 755 file_or_directory
    
    ```
    

Lưu ý rằng để thực hiện các thay đổi này, bạn cần có quyền truy cập thích hợp đối với tệp tin hoặc thư mục đó hoặc cần phải là root hoặc có quyền sudo trên hệ thống.