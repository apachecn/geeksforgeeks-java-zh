# Java 中的数据报

> 原文:[https://www.geeksforgeeks.org/datagrams-in-java/](https://www.geeksforgeeks.org/datagrams-in-java/)

TCP/IP 风格的网络提供了一个序列化的、可预测的、可靠的数据包数据流。然而，这并非没有代价。TCP 包括处理拥挤网络上拥塞控制的算法，以及对数据包丢失的悲观预期。这导致传输数据的方式效率低下。
通过可靠通道(如 TCP 套接字)进行通信的客户端和服务器之间有一个专用的点对点通道。为了通信，他们建立连接，传输数据，然后关闭连接。通过信道发送的所有数据都按照发送的顺序接收。这是由渠道保证的。
相比之下，通过数据报进行通信的应用程序发送和接收完全独立的信息包。这些客户端和服务器没有也不需要专用的点对点通道。无法保证将数据报传送到目的地。他们到达的顺序也不是。

**数据报**

数据报是通过网络发送的独立的、自包含的消息，它的到达、到达时间和内容不能保证。

*   数据报作为一种替代方案发挥着至关重要的作用。
*   数据报是机器之间传递的信息包。一旦数据报被释放到它的预定目标，就不能保证它会到达，甚至不能保证有人会在那里抓住它。
*   同样，当收到数据报时，不能保证它在传输过程中没有被损坏，也不能保证发送它的人仍然在那里接收响应，需要注意的是这一点非常重要。

Java 通过使用两个类在 UDP(用户数据报协议)协议之上实现数据报:

1.  **DatagramPacket** 对象是数据容器。
2.  **DatagramSocket** 是用于发送或接收 DatagramSocket 的机制。

**[DatagramSocket 类](https://www.geeksforgeeks.org/java-net-datagramsocket-class-java/)**

DatagramSocket 定义了四个公共构造函数。它们显示在这里:

*   **DatagramSocket()抛出 SocketException :** 它创建绑定到本地计算机上任何未使用端口的 DatagramSocket。
*   **DatagramSocket(int port)抛出 SocketException :** 它创建一个绑定到端口指定的端口的 DatagramSocket。
*   **DatagramSocket(int port，InetAddress ipAddress)抛出 SocketException :** 它构造一个绑定到指定端口和 InetAddress 的 DatagramSocket。
*   **DatagramSocket(SocketAddress 地址)抛出 SocketException :** 它构造一个绑定到指定 SocketAddress 的 DataGramSocket。

SocketAddress 是一个抽象类，由具体类 InetSocketAddress 实现。InetSocketAddress 用端口号封装一个 IP 地址。如果在创建套接字时发生错误，所有这些都可能引发 SocketException。DatagramSocket 定义了许多方法。其中最重要的两个是 send()和 receive()，如下所示:

*   void send(DatagramPacket 数据包)引发 IOException
*   void receive(DatagramPacket 数据包)引发 IOException

send()方法将数据包发送到数据包指定的端口。接收方法等待从数据包指定的端口接收数据包，并返回结果。
其他方法让您可以访问与 DatagramSocket 关联的各种属性。下面是一个例子:

| 功能 | 使用 |
| --- | --- |
| InetAddress getInetAddress（ ） | 如果套接字已连接，则返回地址。否则，返回 null。 |
| int getLocalPort（ ） | 返回本地端口号。 |
| int getPort() | 返回套接字连接的端口号。如果套接字没有连接到端口，则返回-1。 |
| 布尔 isBound() | 如果套接字绑定到一个地址，则返回 true。否则返回 false。 |
| 布尔 isConnected() | 如果套接字连接到服务器，则返回 true。否则返回 false。 |
| 请参阅 setSoTimeout(int 毫秒)throws SocketException | 将超时周期设置为以毫秒为单位的毫秒数。 |

**[数据包类](https://www.geeksforgeeks.org/java-net-datagrampacket-class-java/)**

DatagramPacket 定义了几个构造函数。这里显示了四个:

*   **DatagramPacket(字节数据[ ]，int size) :** 它指定将接收数据的缓冲区和数据包的大小。它用于通过 DatagramSocket 接收数据
*   **DatagramPacket(字节数据[ ]，int offset，int size) :** 它允许您指定缓冲区中存储数据的偏移量。
*   **DatagramPacket(字节数据[ ]，int size，InetAddress ipAddress，int port) :** 它指定一个目标地址和端口，DatagramSocket 使用这些地址和端口来确定数据包中的数据将被发送到哪里。
*   **DatagramPacket(字节数据[ ]，int 偏移量，int 大小，InetAddress ipAddress，int 端口):**它将从指定偏移量开始的数据包传输到数据中。

把前两种形式想象成构建一个“盒子”，后两种形式想象成填充和寻址一个信封。

DatagramPacket 定义了几种方法，包括这里显示的方法，这些方法允许访问数据包的地址和端口号，以及原始数据及其长度。通常，get 方法用于接收的数据包，set 方法用于发送的数据包。

| 功能 | 使用 |
| --- | --- |
| InetAddress getAddress() | 返回源(对于正在接收的数据报)或目标(对于正在发送的数据报)的地址。 |
| 字节[ ] getData() | 返回数据报中包含的数据的字节数组。主要用于在收到数据报后从数据报中检索数据。 |
| int getLength（ ） | 返回将从 getData()方法返回的字节数组中包含的有效数据的长度。这可能不等于整个字节数组的长度。 |
| 你得到 Offset（ ） | 返回数据的起始索引。 |
| int getPort() | 返回端口号。 |
| 请参阅 inetaddress ipaddress | 设置数据包将被发送到的地址。该地址由 ipAddress 指定。 |
| void setData(字节[ ]日期) | 将数据设置为数据，将偏移量设置为零，将长度设置为数据的字节数 |
| void setData(byte[ ] data，int idx，int size) | 将数据设置为数据，将偏移量设置为 idx，将长度设置为大小。 |
| void setLength(整数大小) | 将数据包的长度设置为大小。 |
| void setPort（int port） | 将端口设置为端口。 |

**数据报示例**

以下示例实现了一个非常简单的网络通信客户端和服务器。消息被输入到服务器的窗口中，并通过网络写到客户端，在客户端显示。

```java
// Java program to illustrate datagrams
import java.net.*;
class WriteServer {

    // Specified server port
    public static int serverPort = 998;

    // Specified client port
    public static int clientPort = 999;

    public static int buffer_size = 1024;
    public static DatagramSocket ds;

    // an array of buffer_size
    public static byte buffer[] = new byte[buffer_size];

    // Function for server
    public static void TheServer() throws Exception
    {
        int pos = 0;
        while (true) {
            int c = System.in.read();
            switch (c) {
            case -1:

                // -1 is given then server quits and returns
                System.out.println("Server Quits.");
                return;
            case '\r':
                break; // loop broken
            case '\n':
                // send the data to client
                ds.send(new DatagramPacket(buffer, pos,
                                           InetAddress.getLocalHost(), clientPort));
                pos = 0;
                break;
            default:
                // otherwise put the input in buffer array
                buffer[pos++] = (byte)c;
            }
        }
    }

    // Function for client
    public static void TheClient() throws Exception
    {
        while (true) {

            // first one is array and later is its size
            DatagramPacket p = new DatagramPacket(buffer, buffer.length);

            ds.receive(p);

            // printing the data which has been sent by the server
            System.out.println(new String(p.getData(), 0, p.getLength()));
        }
    }

    // main driver function
    public static void main(String args[]) throws Exception
    {

        // if WriteServer 1 passed then this will run the server function
        // otherwise client function will run
        if (args.length == 1) {
            ds = new DatagramSocket(serverPort);
            TheServer();
        }
        else {
            ds = new DatagramSocket(clientPort);
            TheClient();
        }
    }
}
```

这个示例程序被 DatagramSocket 构造函数限制在本地机器的两个端口之间运行。要使用该程序，请运行

```java
java WriteServer
```

在一个窗口；这将是客户。那就跑

```java
java WriteServer 1
```

这将是服务器。接收到换行符后，在服务器窗口中键入的任何内容都将被发送到客户端窗口。