# What is the difference between these two commands?
myvar=hello
export myvar=hello

Hai lệnh này liên quan đến việc đặt giá trị cho một biến môi trường trong hệ thống Unix/Linux, nhưng chúng có mục đích khác nhau:

1. `myvar=hello`: Lệnh này tạo một biến cục bộ (local variable) có tên "myvar" và gán giá trị "hello" cho nó. Biến này chỉ có hiệu lực trong phạm vi của tiến trình hiện tại. Nó không được chia sẻ với các tiến trình con hoặc các tiến trình khác.
2. `export myvar=hello`: Lệnh này cũng tạo ra biến "myvar" với giá trị "hello," nhưng nó có hiệu lực là biến môi trường (environment variable) cho tất cả các tiến trình con và các tiến trình khác mà bạn chạy sau đó. Biến môi trường có thể được sử dụng để truyền thông tin giữa các tiến trình và ứng dụng, và chúng thường được sử dụng để cài đặt các biến toàn cục hoặc các cấu hình hệ thống.

Ví dụ, sau khi bạn thực hiện lệnh `export myvar=hello`, biến môi trường "myvar" với giá trị "hello" sẽ có hiệu lực cho tất cả các tiến trình con và các tiến trình sau này trong phiên làm việc hiện tại.

Tóm lại, sự khác biệt chính giữa hai lệnh này là việc sử dụng "export" cho phép biến được sử dụng làm biến môi trường và có hiệu lực cho tất cả các tiến trình con và tiến trình khác, trong khi lệnh đầu tiên chỉ tạo một biến cục bộ có hiệu lực trong tiến trình hiện tại.