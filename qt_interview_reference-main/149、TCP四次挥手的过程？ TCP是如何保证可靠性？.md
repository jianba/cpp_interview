# 149、TCP四次挥手的过程？ TCP是如何保证可靠性？

TCP四次挥手是TCP协议结束连接的过程，其过程如下：


客户端发送FIN包给服务器，表示请求关闭连接。

服务器收到客户端的FIN包后，发送ACK包给客户端，表示确认关闭请求，并且告诉客户端可以关闭连接了。

服务器发送自己的FIN包给客户端，表示请求关闭连接。

客户端收到服务器的FIN包后，发送ACK包给服务器，表示确认关闭请求，并且告诉服务器可以关闭连接了。
TCP协议通过以下几个机制来保证可靠性：

序列号和确认应答：TCP协议在传输数据时，会为每一个数据包设置一个序列号，接收方收到数据包后，需要发送一个确认应答包，告诉发送方收到了哪些数据包。如果发送方没有收到确认应答包，就会重新发送数据包，直到接收方确认收到为止。

超时重传：如果发送方发送了一个数据包，但是没有收到确认应答包，就会重新发送数据包，直到收到确认应答或者达到重传次数上限为止。

滑动窗口：TCP协议中，发送方和接收方都有一个滑动窗口，用来控制数据流的传输。发送方根据接收方的确认应答，动态调整窗口大小，控制数据的发送速度。接收方根据需要，动态调整窗口大小，控制数据的接收速度。

流量控制：TCP协议中，通过滑动窗口来控制数据流的传输，可以防止发送方发送过多的数据，导致接收方无法处理。

拥塞控制：TCP协议中，通过动态调整窗口大小和发送速度，来控制网络拥塞的发生，保证网络的稳定性和可靠性。
通过以上机制，TCP协议可以保证数据的可靠传输，同时也可以保证网络的稳定性和可靠性。 
