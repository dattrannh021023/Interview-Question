# What is the similarity between "ping" & "traceroute" ? How is traceroute able to find the hops.

Cả "ping" và "traceroute" đều là các công cụ được sử dụng để kiểm tra và theo dõi kết nối mạng, nhưng chúng có mục tiêu và phương thức hoạt động khác nhau:

**Ping (Packet Internet Groper):**

- "Ping" được sử dụng để kiểm tra tính khả dụng của một máy chủ hoặc một thiết bị mạng.
- Nó hoạt động bằng cách gửi một gói tin ICMP (Internet Control Message Protocol) đến đích và chờ đợi phản hồi.
- Khi máy chủ hoặc thiết bị nhận được gói tin ICMP, nó sẽ gửi một phản hồi trở lại. Thời gian mà "ping" đo được từ khi gửi gói tin đến khi nhận được phản hồi được sử dụng để đo độ trễ mạng.

**Traceroute:**

- "Traceroute" được sử dụng để xác định đường đi mà các gói tin mạng đi qua từ máy tính của bạn đến một máy chủ hoặc đích khác.
- Nó hoạt động bằng cách gửi nhiều gói tin ICMP với TTL (Time to Live) tăng dần. Mỗi bước, TTL sẽ tăng lên, và khi TTL đạt đến giới hạn, thiết bị trung gian sẽ gửi một thông báo về việc "chuỗi" bị chặn lại. Traceroute lập lại quy trình này với các giá trị TTL tăng dần cho đến khi nó đến được đích.
- Kết quả của "traceroute" là danh sách các máy chủ hoặc thiết bị mạng trung gian mà gói tin đã đi qua để đến đích, cùng với thời gian mà nó mất để đi qua từng bước.

Tóm lại, điểm tương đồng giữa "ping" và "traceroute" là cả hai đều sử dụng gói tin ICMP để tương tác với máy chủ hoặc thiết bị mạng. Tuy nhiên, "ping" chỉ kiểm tra tính khả dụng của một máy chủ cụ thể và đo độ trễ, trong khi "traceroute" giúp xác định đường đi của gói tin qua mạng và liệt kê các bước trung gian trên đường đi. Traceroute thực hiện điều này bằng cách sử dụng TTL để đo lường và theo dõi các bước trung gian.