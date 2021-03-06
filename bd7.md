## TCP如何保证可靠传输？
---

- TCP 使用超时重传 来实现可靠传输：如果一个已经发送的报文段在超时时间内没有收到确认，那么就重传这个报文段。

- 三次握手，保证两端建立连接

- 应用数据被分割成TCP认为最适合发送的数据块。即将数据截断为合理的长度

- TCP收到发自TCP连接另一端的数据，它将发送一个确认

- TCP将保持它首部和数据的检验和。这是一个端到端的检验和。目的是检测数据在传输过程中的任何变化。如果收到的段的检验和有差错，TCP将丢弃这个报文段和不确认收到此报文段。

- TCP 给发送的每一个包进行编号，接收方对数据包进行排序，把有序数据传送给应用层。

- TCP还能提供流量控制。TCP连接的每一方都有固定的缓冲空间。TCP接收端只允许另一端发送接收端缓冲区所能接纳的数据。这将防止较快主机发送数据到较慢主机不会发生缓冲区溢出。

- TCP还能提供拥塞控制。当网络拥塞时，减少数据的发送。