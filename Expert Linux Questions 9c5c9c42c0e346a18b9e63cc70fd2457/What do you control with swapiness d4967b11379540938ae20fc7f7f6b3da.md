# What do you control with swapiness?

`Swappiness` là một tham số quản lý trong hệ thống Linux quyết định mức độ sử dụng swap space (vùng trao đổi) so với bộ nhớ RAM. Giá trị của `swappiness` có thể điều chỉnh để kiểm soát hệ thống sử dụng swap space theo cách mong muốn.

Trong Linux, giá trị `swappiness` thường nằm trong khoảng từ 0 đến 100, với ý nghĩa như sau:

- `swappiness = 0`: Hệ thống sẽ cố gắng tránh sử dụng swap space càng nhiều càng tốt, ưu tiên sử dụng bộ nhớ RAM.
- `swappiness = 100`: Hệ thống sẽ cố gắng sử dụng swap space càng nhiều càng tốt, ưu tiên sử dụng bộ nhớ trên đĩa cứng.

Bằng cách điều chỉnh giá trị `swappiness`, bạn có thể kiểm soát hệ thống làm thế nào để quản lý bộ nhớ khi bộ nhớ RAM bắt đầu bị sử dụng đầy.

Một số ví dụ cụ thể về việc điều chỉnh `swappiness`:

- Nếu bạn muốn hệ thống ưu tiên sử dụng bộ nhớ RAM và hạn chế sử dụng swap space, bạn có thể đặt `swappiness = 10` hoặc thấp hơn.
- Nếu bạn muốn hệ thống sử dụng swap space một cách rộng rãi để giảm áp lực lên bộ nhớ RAM, bạn có thể đặt `swappiness = 60` hoặc cao hơn.

Điều này có thể hữu ích trong việc tối ưu hóa hiệu suất hệ thống và đảm bảo rằng hệ thống sử dụng swap space một cách hiệu quả tùy theo mục đích sử dụng cụ thể của bạn.