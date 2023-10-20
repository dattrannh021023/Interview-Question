# What commands do you know that can be used to check DNS records?

Có một số lệnh và công cụ mà bạn có thể sử dụng để kiểm tra DNS records (bản ghi DNS) trên hệ thống Unix/Linux. Dưới đây là một số trong những lệnh và công cụ phổ biến:

1. **nslookup:** Lệnh `nslookup` cho phép bạn truy vấn thông tin DNS bằng cách chỉ định tên miền hoặc địa chỉ IP. Ví dụ:
    
    ```bash
    nslookup example.com
    
    ```
    
2. **dig (Domain Information Groper):** `dig` là một công cụ mạnh mẽ để truy vấn và hiển thị thông tin DNS. Bạn có thể sử dụng `dig` để truy vấn các loại bản ghi DNS khác nhau, chẳng hạn như A, MX, CNAME, v.v. Ví dụ:
    
    ```bash
    dig example.com A
    
    ```
    
3. **host:** Lệnh `host` cũng cho phép bạn thực hiện truy vấn DNS. Ví dụ:
    
    ```bash
    host example.com
    
    ```
    
4. **ping:** Mặc dù lệnh `ping` chủ yếu được sử dụng để kiểm tra tính khả dụng của máy chủ, nhưng nó cũng có thể hiển thị địa chỉ IP của một tên miền:
    
    ```bash
    ping example.com
    
    ```
    
5. **whois:** `whois` là một công cụ để truy vấn thông tin về chủ sở hữu tên miền và thông tin liên hệ. Ví dụ:
    
    ```bash
    whois example.com
    
    ```
    

Các lệnh và công cụ này giúp bạn kiểm tra và thu thập thông tin về DNS records của một tên miền hoặc địa chỉ IP cụ thể trên hệ thống Unix/Linux.