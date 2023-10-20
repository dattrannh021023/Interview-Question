# What is ARP and what is it used for?

ARP (Address Resolution Protocol) là một giao thức mạng được sử dụng để ánh xạ địa chỉ MAC (Media Access Control) của một thiết bị mạng vào địa chỉ IP của nó trong mạng Ethernet. ARP có vai trò quan trọng trong việc kết nối và giao tiếp giữa các thiết bị trên cùng một mạng LAN.

Cơ chế hoạt động của ARP như sau:

1. Khi một thiết bị muốn gửi dữ liệu đến một địa chỉ IP trên cùng mạng LAN, nó sẽ kiểm tra xem liệu địa chỉ MAC tương ứng với địa chỉ IP đó đã được lưu trữ trong bộ nhớ cache ARP (ARP cache) của nó hay chưa.
2. Nếu địa chỉ MAC chưa có trong bộ nhớ cache ARP, thiết bị sẽ gửi một yêu cầu ARP (ARP request) broadcast ra mạng LAN. Yêu cầu này chứa địa chỉ IP mà thiết bị muốn ánh xạ thành địa chỉ MAC.
3. Tất cả các thiết bị trong mạng LAN đều nhận được yêu cầu ARP, nhưng chỉ thiết bị có địa chỉ IP tương ứng mới phản hồi bằng một thông điệp ARP reply. Thông điệp này chứa địa chỉ MAC của thiết bị đó.
4. Sau khi thiết bị gửi yêu cầu ARP nhận được thông điệp ARP reply, nó lưu trữ địa chỉ MAC này vào bộ nhớ cache ARP của mình để sử dụng cho các lần truyền dữ liệu sau.

ARP được sử dụng trong mạng LAN để định vị và liên kết giữa địa chỉ IP và địa chỉ MAC của các thiết bị. Điều này cho phép các thiết bị trên cùng mạng LAN truyền dữ liệu cho nhau bằng cách sử dụng địa chỉ MAC, giúp thiết lập kết nối và giao tiếp trong mạng Ethernet.