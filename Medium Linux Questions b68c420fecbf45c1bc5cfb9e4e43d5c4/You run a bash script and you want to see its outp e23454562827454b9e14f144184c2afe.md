# You run a bash script and you want to see its output on your terminal and save it to a file at the same time. How could you do it?

Để xem đầu ra của một tệp lệnh bash trên màn hình và đồng thời lưu nó vào một tệp, bạn có thể sử dụng ký tự đường ống (pipe) để chuyển đầu ra từ tệp lệnh sang cả màn hình và tệp. Dưới đây là cách bạn có thể thực hiện điều đó:

```bash
./your_script.sh | tee output.txt

```

Trong đó:

- `./your_script.sh` là tệp lệnh bash của bạn.
- `|` là ký tự đường ống (pipe), nó chuyển đầu ra của tệp lệnh bên trái của nó sang tệp lệnh bên phải của nó.
- `tee` là một tiện ích dòng lệnh cho phép bạn hiển thị đầu ra trên màn hình và ghi nó vào một tệp cùng một lúc.
- `output.txt` là tên tệp mà bạn muốn lưu đầu ra của tệp lệnh vào.

Khi bạn chạy lệnh này, bạn sẽ thấy đầu ra của tệp lệnh trên màn hình và cùng lúc đó, nó cũng sẽ được ghi vào tệp `output.txt`.