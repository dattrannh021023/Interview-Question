# How can you get Host, Channel, ID, LUN of SCSI disk?

Để lấy thông tin Host, Channel, ID và LUN của một ổ đĩa SCSI trong hệ thống Linux, bạn có thể sử dụng lệnh `lsscsi` hoặc `lsscsi -g`. Để sử dụng các lệnh này, bạn cần có quyền quản trị hệ thống (superuser hoặc sudo).

1. Sử dụng lệnh `lsscsi`:
    
    ```
    lsscsi
    
    ```
    
    Kết quả sẽ liệt kê tất cả các thiết bị SCSI được phát hiện trong hệ thống, bao gồm Host, Channel, ID và LUN của mỗi thiết bị.
    
2. Sử dụng lệnh `lsscsi -g`:
    
    ```
    lsscsi -g
    
    ```
    
    Lệnh này cung cấp thông tin chi tiết hơn về các thiết bị SCSI, bao gồm Host, Channel, ID, LUN và các thông tin khác như đường dẫn thiết bị.
    

Kết quả trả về bởi cả hai lệnh sẽ giúp bạn xác định thông tin Host, Channel, ID và LUN của ổ đĩa SCSI trong hệ thống của bạn.