# You ran a binary and nothing happened. How would you debug this?

Khi bạn chạy một tệp nhị phân (binary) và không có gì xảy ra, có một số bước bạn có thể thực hiện để gỡ lỗi (debug) vấn đề này:

1. **Kiểm tra quyền thực thi:** Đảm bảo rằng tệp nhị phân có quyền thực thi. Bạn có thể kiểm tra điều này bằng lệnh `ls -l` và đảm bảo rằng bit thực thi (x) được đặt cho tệp.
2. **Kiểm tra xem tệp nhị phân có bất kỳ lỗi nào không:** Bạn có thể chạy lệnh `file` để xác định kiểu của tệp nhị phân và sử dụng các công cụ như `readelf` hoặc `objdump` để kiểm tra tệp nhị phân có lỗi không.
3. **Kiểm tra các thông báo lỗi:** Mở một cửa sổ terminal riêng biệt và chạy tệp nhị phân từ đó. Nếu có bất kỳ lỗi nào xuất hiện trên terminal, chúng có thể giúp bạn xác định vấn đề.
4. **Kiểm tra tệp nhị phân bằng một trình gỡ lỗi (debugger):** Bạn có thể sử dụng các trình gỡ lỗi như GDB (GNU Debugger) để theo dõi quá trình thực thi của tệp nhị phân và xác định điểm dừng hoặc lỗi.
5. **Kiểm tra các yêu cầu hệ thống:** Một số ứng dụng cần các thư viện hoặc phụ thuộc hệ thống khác để hoạt động. Hãy kiểm tra xem tệp nhị phân có đủ yêu cầu này không.
6. **Kiểm tra quyền truy cập tệp:** Đảm bảo rằng tệp nhị phân có quyền truy cập vào các tệp và thư mục mà nó cần để hoạt động.
7. **Kiểm tra tệp nhị phân với lệnh `strace`:** Bạn có thể sử dụng lệnh `strace` để theo dõi các cuộc gọi hệ thống mà tệp nhị phân thực hiện và xem xét xem nó bị kẹt ở đâu.
8. **Kiểm tra log hệ thống:** Xem trong tệp nhật ký hệ thống (system log) như `/var/log/messages` hoặc `/var/log/syslog` để xem xem có thông tin gỡ lỗi nào được ghi lại.
9. **Kiểm tra phiên bản kernel và kiến thức về tệp nhị phân:** Đôi khi, tệp nhị phân yêu cầu phiên bản kernel cụ thể hoặc kiến thức về hệ thống cụ thể. Kiểm tra xem tệp nhị phân có yêu cầu gì không.
10. **Kiểm tra tệp nhị phân trên một hệ thống khác:** Nếu bạn có một hệ thống khác, hãy thử chạy tệp nhị phân trên đó để xem nó hoạt động được không. Điều này có thể giúp xác định xem vấn đề có liên quan đến hệ thống cụ thể hay không.

Khi bạn thực hiện các bước trên, bạn có thể xác định được nguyên nhân tại sao tệp nhị phân không hoạt động và tiến hành sửa chữa vấn đề đó.