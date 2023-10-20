# What is the difference between a "left" and a "right" join?

Câu hỏi này liên quan đến ngôn ngữ truy vấn SQL và một phần của SQL JOIN. Trong SQL, có hai loại JOIN phổ biến: LEFT JOIN và RIGHT JOIN. Cả hai loại này được sử dụng để kết hợp dữ liệu từ hai hoặc nhiều bảng trong cơ sở dữ liệu, nhưng có sự khác nhau về cách nó hoạt động:

1. LEFT JOIN:
    - LEFT JOIN trả về tất cả các hàng từ bảng bên trái (bảng 1) và các hàng từ bảng bên phải (bảng 2) mà khớp với điều kiện JOIN.
    - Nếu không có sự khớp từ bảng bên phải, các cột từ bảng bên phải sẽ được thay bằng giá trị NULL.
    - Dữ liệu từ bảng bên trái sẽ luôn được bảo toàn, và các hàng từ bảng bên phải chỉ được thêm vào nếu có sự khớp với bảng bên trái.
2. RIGHT JOIN:
    - RIGHT JOIN hoạt động ngược lại với LEFT JOIN. Nó trả về tất cả các hàng từ bảng bên phải (bảng 2) và các hàng từ bảng bên trái (bảng 1) mà khớp với điều kiện JOIN.
    - Nếu không có sự khớp từ bảng bên trái, các cột từ bảng bên trái sẽ được thay bằng giá trị NULL.
    - Dữ liệu từ bảng bên phải sẽ luôn được bảo toàn, và các hàng từ bảng bên trái chỉ được thêm vào nếu có sự khớp với bảng bên phải.

Tóm lại, sự khác biệt giữa LEFT JOIN và RIGHT JOIN là cơ cấu của bảng bên trái và bên phải trong kết quả trả về. LEFT JOIN giữ nguyên bảng bên trái và có thể thêm giá trị NULL từ bảng bên phải, trong khi RIGHT JOIN giữ nguyên bảng bên phải và có thể thêm giá trị NULL từ bảng bên trái. Lựa chọn giữa LEFT JOIN và RIGHT JOIN phụ thuộc vào nhu cầu của bạn về dữ liệu từ các bảng tham gia trong truy vấn SQL.