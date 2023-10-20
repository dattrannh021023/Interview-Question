# What is a level 0 backup? What is an incremental backup?

A **level 0 backup** is a `full backup` of all data. It is the most comprehensive type of backup, but it can also be the most `time-consuming` and `expensive`.

An **incremental backup** is a `backup of all data that has changed since the previous backup`. This can be either a level 0 backup or a previous incremental backup. Incremental backups are `faster` and `less expensive` than level 0 backups, but they do `require` that you have `a previous backup` to restore from.

Level 0 backups and incremental backups are often used together to create a comprehensive and efficient backup strategy. For example, you might do a `level 0 backup at the beginning of each week` and then `incremental backups each day`. This way, you would always have a full backup of your data less than a week old, and you could quickly restore from a previous day's backup if needed.

Here is an example of how a level 0 backup and incremental backups might be used:

- **Monday:** Level 0 backup of all data
- **Tuesday:** Incremental backup of all data that has changed since Monday
- **Wednesday:** Incremental backup of all data that has changed since Tuesday
- **Thursday:** Incremental backup of all data that has changed since Wednesday
- **Friday:** Incremental backup of all data that has changed since Thursday

If there is a problem on Friday, you can restore from the Thursday incremental backup. If there is a problem on Monday, you can restore from the Monday level 0 backup.

Level 0 backups and incremental backups can be used with a variety of backup technologies, such as tape, disk, and cloud storage. The best backup technology for you will depend on your specific needs and budget.

Một "level 0 backup" và một "incremental backup" là hai loại sao lưu dữ liệu trong quản lý lưu trữ thông tin và dữ liệu máy tính:

1. **Level 0 Backup (Full Backup):**
    - Level 0 Backup, còn được gọi là Full Backup, là một loại sao lưu dữ liệu trong đó toàn bộ dữ liệu hoặc một tập hợp dữ liệu được sao chép hoàn toàn từ nguồn gốc đến nơi lưu trữ dự phòng.
    - Khi thực hiện một level 0 backup, tất cả các tệp và thư mục được sao chép mà không quan tâm đến việc chúng đã thay đổi hay không. Điều này đảm bảo rằng bản sao lưu chứa toàn bộ dữ liệu vào thời điểm sao lưu.
    - Level 0 Backup thường tốn nhiều dung lượng lưu trữ và thời gian sao lưu, nhưng cho phép khôi phục dữ liệu một cách nhanh chóng và đầy đủ.
2. **Incremental Backup:**
    - Incremental Backup là một loại sao lưu dữ liệu chỉ sao chép các thay đổi từ lần sao lưu trước đó đến thời điểm hiện tại. Thay vì sao chép toàn bộ dữ liệu, nó chỉ sao chép các tệp và thư mục mới hoặc đã thay đổi kể từ lần sao lưu trước đó.
    - Ví dụ: Nếu bạn đã thực hiện một Level 0 Backup vào thứ Hai và sau đó thực hiện các Incremental Backup vào thứ Ba, thứ Tư và thứ Năm, thì các Incremental Backup sẽ chỉ sao chép các thay đổi từng ngày thay vì toàn bộ dữ liệu.
    - Incremental Backup tiết kiệm dung lượng lưu trữ và thời gian sao lưu so với Level 0 Backup, nhưng quá nhiều bản Incremental Backup có thể tạo ra quá trình phục hồi phức tạp hơn.

Một cách tổ chức thông thường là sử dụng Level 0 Backup định kỳ (ví dụ: hàng tuần hoặc hàng tháng) để tạo ra một bản sao lưu đầy đủ và sau đó sử dụng Incremental Backup hàng ngày để ghi lại các thay đổi hàng ngày. Khi cần khôi phục dữ liệu, bạn sẽ cần cả Level 0 Backup và tất cả các bản Incremental Backup từ thời điểm Level 0 Backup được tạo đến thời điểm khôi phục.