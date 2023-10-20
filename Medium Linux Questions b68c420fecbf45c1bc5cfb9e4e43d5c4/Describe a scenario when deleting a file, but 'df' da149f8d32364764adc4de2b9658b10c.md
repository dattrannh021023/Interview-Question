# Describe a scenario when deleting a file, but 'df' not showing the space being freed.

Một trường hợp mà bạn có thể gặp khi xóa một tệp nhưng lệnh `df` không cho thấy không gian đã được giải phóng là khi tệp đó đang được một tiến trình sử dụng (chẳng hạn là một tiến trình chạy) và vẫn đang được giữ bởi tiến trình này. Khi bạn xóa tệp nhưng nó vẫn đang được sử dụng bởi một tiến trình, không gian lưu trữ được sử dụng bởi tệp này không thể được giải phóng cho đến khi tiến trình đó thả tệp hoặc kết thúc.

Dưới đây là một ví dụ cụ thể:

1. **Tiến trình đang sử dụng một tệp lớn:** Giả sử bạn có một tệp lớn đang được một ứng dụng hoặc tiến trình nào đó sử dụng. Khi bạn xóa tệp này bằng lệnh `rm`, nó sẽ bị xóa khỏi hệ thống tệp và không còn xuất hiện trong hệ thống tệp nữa. Tuy nhiên, tiến trình vẫn giữ tệp trong bộ nhớ và tiếp tục sử dụng nó.
2. **Không gian bị giữ bởi tiến trình:** Mặc dù tệp đã bị xóa, không gian lưu trữ mà tệp đó sử dụng vẫn không thể được giải phóng cho đến khi tiến trình sử dụng nó kết thúc hoặc thả tệp.
3. **Lệnh `df` không thể thấy:** Lệnh `df` không thể nhìn thấy không gian đã được giải phóng cho đến khi không còn tiến trình nào giữ tệp đó. Điều này có nghĩa rằng trong một khoảng thời gian, `df` sẽ không thể thấy sự thay đổi trong không gian lưu trữ cho đến khi tiến trình kết thúc.

Để giải quyết vấn đề này, bạn có thể thực hiện các bước sau:

1. **Xác định tiến trình đang giữ tệp:** Sử dụng lệnh `lsof` (list open files) để xem xem tệp nào đang được mở bởi tiến trình nào:
    
    ```bash
    lsof | grep deleted
    
    ```
    
    Lệnh này sẽ liệt kê tất cả các tệp đã bị xóa mà vẫn đang được giữ bởi các tiến trình.
    
2. **Kết thúc hoặc thả tệp từ tiến trình đó:** Tìm tiến trình đang giữ tệp và kết thúc hoặc thả tệp từ tiến trình đó. Sau đó, không gian lưu trữ sẽ được giải phóng và `df` sẽ hiển thị sự thay đổi.
3. **Thực hiện lại lệnh `df`:** Sau khi giải phóng không gian lưu trữ, thực hiện lại lệnh `df` để kiểm tra xem không gian đã được giải phóng chưa.