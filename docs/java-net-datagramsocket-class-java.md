# Java 中的 Java.net.DatagramSocket 类

> 原文:[https://www . geesforgeks . org/Java-net-datagramsocket-class-Java/](https://www.geeksforgeeks.org/java-net-datagramsocket-class-java/)

数据报套接字是一种网络套接字，它为发送和接收数据包提供无连接点。从数据报套接字发送的每个数据包都是单独路由和传递的。它还可以用于发送和接收广播消息。数据报套接字是 java 通过 UDP 而不是 TCP 提供网络通信的机制。

**施工人员:**

**1。DatagramSocket() :** 创建一个 DatagramSocket，并将其绑定到本地机器上的任何可用端口。如果使用这个构造函数，操作系统会将任何端口分配给这个套接字。

```java
Syntax :public DatagramSocket()
               throws SocketException
Throws :
SocketException : if the socket could not be opened
```

**2。DatagramSocket(DatagramSocketImpl impl):**用给定的 DatagramSocket 创建一个未绑定的数据报套接字。

```java
Syntax :protected DatagramSocket(DatagramSocketImpl impl)
Parameters :
impl : instance of datagramScketImpl
```

**3。数据报套接字(int 端口):**创建数据报套接字并将其绑定到指定端口。套接字将绑定到内核选择的通配符地址。

```java
Syntax : public DatagramSocket(int port)
               throws SocketException
Parameters : 
port : port number to bind this socket to
```

**4。DatagramSocket(int port，InetAddress ladder):**构造一个数据报套接字，并将其绑定到指定的端口和 InetAddress。

```java
Syntax : public DatagramSocket(int port,
              InetAddress laddr)
               throws SocketException
Parameters :
port : local port to bind
laddr : local address to bind
Throws :
SocketException : If the socket could not be opened
```

**5。DatagramSocket(SocketAddress bindaddr):**构造一个新的套接字对象，并将其绑定到指定的套接字地址(IP 地址+端口号)。

```java
Syntax :public DatagramSocket(SocketAddress bindaddr)
               throws SocketException
Parameters :
bindaddr : socket address to bind to
Throws : 
SocketException : If socket could not be opened
```

**方法:**

**1。bind() :** 将此套接字绑定到指定的地址和端口号。

```java
Syntax : public void bind(SocketAddress addr)
Parameters : 
addr : socket address to bind to
```

**2。connect() :** 连接到指定的地址和端口。连接到远程主机后，该套接字只能发送或接收来自该远程主机的数据包。如果无法与指定的远程主机建立连接，对 send()或 receive()的调用将引发可预测异常。

```java
Syntax :public void connect(InetAddress address,
           int port)
Parameters :
address : address of remote host
port : port number of remote host
```

另一个重载方法将套接字地址作为参数。

```java
Syntax :public void connect(SocketAddress address)
Parameters :
address : socket address of remote host
```

**3。断开():**断开插座。如果插座没有连接，那么这个方法没有效果。

```java
Syntax :public void disconnect()
```

**4。isBound() :** 返回一个布尔值，指示此套接字是否绑定。

```java
Syntax :public boolean isBound()
```

isConnected() : 返回一个布尔值，指示此套接字是否已连接。

```java
Syntax :public boolean isConnected()
```

**5。isConnected() :** 返回表示套接字连接状态的布尔值。请注意，即使在关闭套接字之后，如果在关闭套接字之前连接了此套接字，此方法也将继续返回 true。

```java
Syntax :public boolean isConnected()
```

**6。getnetaddress():**返回这个套接字连接到的地址。

```java
Syntax : public InetAddress getInetAddress()
```

**7。getPort() :** 返回该套接字所连接的机器上的端口。

```java
Syntax : public int getPort()
```

**8。getRemoteSocketAddress() :** 返回该套接字所连接的套接字地址(IP 地址+端口号)。

```java
Syntax : public SocketAddress getRemoteSocketAddress()
```

**9。getLocalSocketAddress() :** 返回该套接字绑定到的机器的地址，即本地机器套接字地址。

```java
public SocketAddress getLocalSocketAddress()
```

**10。send() :** 从此套接字发送数据报数据包。应该注意的是，关于要发送的数据的信息、它被发送到的地址等都是由分组本身处理的。

```java
Syntax : public void send(DatagramPacket p)
Parameters :
p : packet to send
```

**11 时。receive() :** 用于接收来自发送方的数据包。当一个包被成功接收时，包的缓冲区被接收的消息填满。数据包还包含有价值的信息，如发件人地址和端口号。该方法一直等到收到数据包。

```java
Syntax : public void receive(DatagramPacket p)
Parameters : 
p : datagram packet into which incoming data is filled
```

**12 时。getLocalAddress() :** 返回此套接字绑定到的本地地址。

```java
Syntax : public InetAddress getLocalAddress()
```

**13。getLocalPort() :** 返回套接字绑定到的本地机器上的端口。

```java
Syntax : public int getLocalPort()
```

**14。setSOTimeout() :** 用于设置接收数据报包的等待时间。由于对 receive()方法的调用会无限期地阻止程序的执行，直到收到数据包，因此该方法可用于限制该时间。一旦指定的时间过期，就会引发 Java . net . SockettimeOutException。

```java
Syntax : public void setSoTimeout(int timeout)
Parameters :
timeout : time to wait
```

**15。getSoTimeout() :** 返回超时参数(如果指定)，或者返回 0(表示无限时间)。

```java
Syntax : public int getSoTimeout()
```

**16。setSendBufferSize() :** 用于设置可从此套接字发送的数据包的最大大小限制。它设置了 SO_SNDBUF 选项，网络实现使用该选项来设置底层网络缓冲区的大小。当发送速率较高时，增加大小可以允许在发送之前对数据包进行排队。

```java
Syntax : public void setSendBufferSize(int size)
Parameters : 
size : size of send buffer to set
```

**Java 实现:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
import java.io.IOException;
import java.net.DatagramPacket;
import java.net.DatagramSocket;
import java.net.InetAddress;
import java.util.Arrays;

public class datasocket 
{
    public static void main(String[] args) throws IOException 
    {
        // Constructor to create a datagram socket
        DatagramSocket socket = new DatagramSocket();
        InetAddress address = InetAddress.getByName("localhost");
        int port = 5252;
        byte buf[] = { 12, 13 };
        byte buf1[] = new byte[2];
        DatagramPacket dp = new DatagramPacket(buf, 2, address, port);
        DatagramPacket dptorec = new DatagramPacket(buf1, 2);

        // connect() method
        socket.connect(address, port);

        // isBound() method
        System.out.println("IsBound : " + socket.isBound());

        // isConnected() method
        System.out.println("isConnected : " + socket.isConnected());

        // getInetAddress() method
        System.out.println("InetAddress : " + socket.getInetAddress());

        // getPort() method
        System.out.println("Port : " + socket.getPort());

        // getRemoteSocketAddress() method
        System.out.println("Remote socket address : " + 
                         socket.getRemoteSocketAddress());

        // getLocalSocketAddress() method
        System.out.println("Local socket address : " + 
                          socket.getLocalSocketAddress());

        // send() method
        socket.send(dp);
        System.out.println("...packet sent successfully....");

        // receive() method
        socket.receive(dptorec);
        System.out.println("Received packet data : " + 
                          Arrays.toString(dptorec.getData()));

        // getLocalPort() method
        System.out.println("Local Port : " + socket.getLocalPort());

        // getLocalAddress() method
        System.out.println("Local Address : " + socket.getLocalAddress());

        // setSOTimeout() method
        socket.setSoTimeout(50);

        // getSOTimeout() method
        System.out.println("SO Timeout : " + socket.getSoTimeout());
    }

}
```

为了测试上述程序，需要一个小的服务器程序来接收发送的数据包并实现 receive()方法。其实现如下。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
import java.io.IOException;
import java.net.DatagramPacket;
import java.net.DatagramSocket;
public class smallserver {

    public static void main(String[] args) throws IOException {

        DatagramSocket ds = new DatagramSocket(5252);
        byte buf[] = new byte[2];
        byte send[] = { 13, 18 };
        DatagramPacket dp = new DatagramPacket(buf, 2);

        ds.receive(dp);

        DatagramPacket senddp = new DatagramPacket(send, 2, 
                               dp.getAddress(), dp.getPort());
        ds.send(senddp);
    }

}
```

**输出:**在客户端

```java
IsBound : true
isConnected : true
InetAddress : localhost/127.0.0.1
Port : 5252
Remote socket address : localhost/127.0.0.1:5252
Local socket address : /127.0.0.1:59498
packet sent successfully
Received packet data : [13, 18]
Local Port : 59498
Local Address : /127.0.0.1
SO Timeout : 50
```

**17。getSendBufferSize() :** 返回这个套接字的 SO_SNDBUF 选项的值。

```java
Syntax : public int getSendBufferSize()
```

**18。setReceiveBufferSize() :** 用于设置在此套接字上接收的数据包的最大大小限制。它设置了 SO_RCVBUF 选项，网络实现使用该选项来设置底层网络缓冲区的大小。当数据包发送速度快于消耗速度时，增加大小可以允许在接收端对数据包进行排队。

```java
Syntax : public void setReceiveBufferSize(int size)
Parameters : 
size : size of receive buffer to set
```

**19。getReceiveBufferSize() :** 返回这个套接字的 SO_RCVBUF 选项的值。

```java
Syntax : public int getReceiveBufferSize()
```

**20。setReuseAddress() :** 有时可能需要将多个套接字绑定到同一个地址。启用此选项可使其他套接字绑定到与此相同的地址。必须在调用 bind()之前设置它。它设置 SO_REUSEADDR 套接字选项的值。

```java
Syntax : public void setReuseAddress(boolean on)
Parameters : 
on : true for enable, false otherwise
```

**21。getReuseAddress() :** 返回指示 SO_REUSEADDR 套接字选项设置的布尔值。

```java
Syntax : public boolean getReuseAddress()
```

**22。setBroadcast() :** 设置 SO_BROADCAST 套接字选项的值。

```java
Syntax : public void setBroadcast(boolean on)
Parameters : 
on : true to allow broadcast, false otherwise
```

**23。getBroadcast() :** 如果启用了广播，则返回 true，否则返回 false。

```java
Syntax : public boolean getBroadcast()
```

**24。setTrafficClass() :** 用于设置从这个 DatagramSocket 发送的数据报的 IP 数据报头中的服务类型八位字节。关于流量的更多细节，请参考[维基百科](https://en.wikipedia.org/wiki/Type_of_service)

```java
Syntax : public void setTrafficClass(int tc)
Parameters : 
tc : int value of bitset, 0<=tc<=255
```

**25。getTrafficClass() :** 从这个套接字发送的数据包的 IP 头中获取流量类或服务类型。

```java
Syntax : public int getTrafficClass()
```

**26。close() :** 关闭这个数据报套接字。任何挂起的接收调用都会引发 SocketException。

```java
Syntax : public void close()
```

**27。isClosed() :** 返回指示套接字是否关闭的布尔值。

```java
Syntax : public boolean isClosed()
```

**28。getChannel() :** 返回与此套接字关联的数据通道(如果有)。关于数据报通道的更多细节可以在[官方 Java 文档](https://docs.oracle.com/javase/7/docs/api/java/nio/channels/DatagramChannel.html)中找到。

```java
Syntax : public DatagramChannel getChannel()
```

**29。setDatagramSocketImplFactory():**为应用程序设置数据报套接字实现工厂。

```java
Syntax :public static void setDatagramSocketImplFactory(
                                 DatagramSocketImplFactory fac)
Parameters : 
fac - the desired factory.
Throws : 
IOException - if an I/O error occurs when setting the datagram socket factory.
SocketException - if the factory is already defined.
```

**Java 实现:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
import java.io.IOException;
import java.net.DatagramSocket;

public class datasock2 {

    public static void main(String[] args) throws IOException {

        // Constructor
        DatagramSocket socket = new DatagramSocket(1235);

        // setSendBufferSize() method
        socket.setSendBufferSize(20);

        // getSendBufferSize() method
        System.out.println("Send buffer size : " + 
                         socket.getSendBufferSize());

        // setReceiveBufferSize() method
        socket.setReceiveBufferSize(20);

        // getReceiveBufferSize() method
        System.out.println("Receive buffer size : " + 
                           socket.getReceiveBufferSize());

        // setReuseAddress() method
        socket.setReuseAddress(true);

        // getReuseAddress() method
        System.out.println("SetReuse address : " + 
                             socket.getReuseAddress());

        // setBroadcast() method
        socket.setBroadcast(false);

        // getBroadcast() method
        System.out.println("setBroadcast : " + 
                              socket.getBroadcast());

        // setTrafficClass() method
        socket.setTrafficClass(45);

        // getTrafficClass() method
        System.out.println("Traffic class : " + 
                           socket.getTrafficClass());

        // getChannel() method
        System.out.println("Channel : " + 
       ((socket.getChannel()!=null)?socket.getChannel():"null"));

        // setSocketImplFactory() method
        socket.setDatagramSocketImplFactory(null);

        // close() method
        socket.close();

        // isClosed() method
        System.out.println("Is Closed : " + socket.isClosed());

    }
}
```

**输出:**

```java
Send buffer size : 20
Receive buffer size : 20
SetReuse address : true
setBroadcast : false
Traffic class : 44
Channel : null
Is Closed : true
```

**参考资料:** [官方 Java 文档](https://docs.oracle.com/javase/7/docs/api/java/net/DatagramSocket.html)

本文由**里沙布·马赫塞**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。