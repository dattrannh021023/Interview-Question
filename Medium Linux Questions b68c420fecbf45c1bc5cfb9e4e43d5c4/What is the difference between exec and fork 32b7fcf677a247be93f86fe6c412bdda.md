# What is the difference between exec and fork?

`exec()` và `fork()` là hai hàm quan trọng trong hệ thống Unix/Linux để tạo các tiến trình mới và thay đổi chương trình được thực thi trong một tiến trình hiện tại. Dưới đây là sự khác biệt chính giữa chúng:

1. **fork():**
    - `fork()` là một hàm dùng để tạo một bản sao (child process) của tiến trình gọi `fork()`. Sau khi gọi `fork()`, sẽ có hai tiến trình: tiến trình cha (parent process) và tiến trình con (child process).
    - Tiến trình cha và tiến trình con chia sẻ cùng mã máy (code) và dữ liệu của tiến trình cha ban đầu, nhưng chúng có không gian địa chỉ riêng, vì vậy các thay đổi trong không gian địa chỉ của một tiến trình không ảnh hưởng đến tiến trình khác.
    - `fork()` thường được sử dụng để tạo một tiến trình con độc lập để thực hiện các công việc khác nhau so với tiến trình cha.
2. **exec():**
    - `exec()` là một hàm dùng để thay đổi chương trình được thực thi trong một tiến trình hiện tại. Thay đổi này xảy ra trong cùng một tiến trình, không tạo ra một tiến trình con mới như `fork()`.
    - Khi gọi `exec()`, tiến trình hiện tại bị thay thế bởi một chương trình khác. Điều này có nghĩa rằng mã máy và không gian địa chỉ của tiến trình được thay đổi để thực thi chương trình mới.
    - `exec()` thường được sử dụng để thay đổi chương trình của một tiến trình để thực hiện một nhiệm vụ khác mà không cần tạo ra một tiến trình con mới.

Tóm lại, `fork()` được sử dụng để tạo ra một tiến trình con riêng biệt, trong khi `exec()` được sử dụng để thay đổi chương trình của tiến trình hiện tại. Khi kết hợp cùng nhau, `fork()` và `exec()` có thể sử dụng để tạo ra một tiến trình con mới và sau đó thay đổi chương trình của nó để thực hiện công việc cụ thể.