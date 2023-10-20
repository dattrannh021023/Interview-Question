# What is command used to show the routing table on a Linux box?

Lệnh được sử dụng để hiển thị bảng định tuyến (routing table) trên một hệ thống Linux là `route` hoặc `ip route`. Dưới đây là cách sử dụng cả hai lệnh này:

1. Sử dụng lệnh `route`:
    
    ```
    route -n
    
    ```
    
    Lệnh này sẽ hiển thị bảng định tuyến trong định dạng số học (không sử dụng tên miền) và cột "Gateway" sẽ không được hiển thị.
    
2. Sử dụng lệnh `ip route`:
    
    ```
    ip route show
    
    ```
    
    Lệnh này cung cấp thông tin chi tiết hơn về bảng định tuyến và hiển thị cả tên miền và địa chỉ IP của các cổng (gateway) đối với từng mục trong bảng định tuyến.
    

Cả hai lệnh đều cho phép bạn xem cách các gói dữ liệu sẽ được định tuyến trong hệ thống Linux của bạn.