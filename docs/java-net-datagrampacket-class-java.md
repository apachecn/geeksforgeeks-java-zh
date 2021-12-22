# Java 中的 Java . net . DataGramppacket 类

> 原文:[https://www . geesforgeks . org/Java-net-datagram packet-class-Java/](https://www.geeksforgeeks.org/java-net-datagrampacket-class-java/)

这个类为消息从一个系统到另一个系统的无连接传输提供了便利。每个消息仅基于包含在分组中的信息进行路由，并且不同的分组可能进行不同的路由。也不能保证消息是否会被传递，它们也可能无序到达。这个类提供了使用数据报套接字类创建用于无连接传递的数据报包的机制。
**构造函数:**构造函数根据其用途而变化，即用于接收或发送数据包。这些构造函数中使用的重要参数是-

1.  **buf** :这是要传递或接收的实际消息。数据报包接收或发送填充在字节数组中的数据。如果在构造函数中使用它来发送消息，那么它代表要传递的消息，当用于接收目的时，它代表将存储接收到的消息的缓冲区。
2.  **偏移量**:表示进入缓冲阵列的偏移量。
3.  **长度:**是要接收的数据包的实际大小。这必须小于或等于缓冲区数组的大小，否则会出现溢出，因为接收到的消息无法容纳在数组中。
4.  **地址**:这是消息要传递到的目的地。
5.  **端口**:这是消息要传递到的端口。
6.  **SocketAddress**:关于地址和端口的信息可以借助 socket address 来表示。功能与以上两者结合相同。

**发送目的**，使用以下构造函数:

```
Syntax :public DatagramPacket(byte[] buf,
              int offset,
              int length,
              InetAddress address,
              int port)
Parameters :
buf : byte array
offset : offset into the array
length : length of message to deliver
address : address of destination
port : port number of destination
```

```
Syntax :public DatagramPacket(byte[] buf,
              int offset,
              int length,
              SocketAddress address)
Parameters :
buf : byte array
offset : offset into the array
length : length of message to deliver
address : socket address of destination
```

```
Syntax :public DatagramPacket(byte[] buf,
              int length,
              InetAddress address,
              int port)
Parameters :
buf : byte array
length : length of message to deliver
address : address of destination
port : port number of destination
```

```
Syntax :public DatagramPacket(byte[] buf,
              int length,
              SocketAddress address)
Parameters :
buf : byte array
length : length of message to deliver
address : socket address of destination
```

**为了接收目的**，使用了以下构造函数:

```
Syntax :public DatagramPacket(byte[] buf,
              int offset,
              int length)
Parameters :
buf : byte array
offset : offset into the array
length : length of message to deliver
```

```
Syntax :public DatagramPacket(byte[] buf,
              int length)
Parameters :
buf : byte array
length : length of message to deliver
```

**方法:**

1.  **getAddress() :** 返回数据包发送到的或接收到的 IP 地址。

```
Syntax :public InetAddress getAddress()
```

1.  **getPort() :** 返回数据包发送到的端口或接收到数据包的端口。此方法专门用于服务器获取发送请求的客户端的端口。

```
Syntax : public int getPort()
```

1.  **getData() :** 以字节数组的形式返回此数据包中包含的数据。数据从指定的偏移量开始，具有指定的长度。

```
Syntax : public byte[] getData()
```

1.  **getOffset() :** 返回指定的偏移量。

```
Syntax : public int getOffset()
```

1.  **getLength() :** 返回要发送或接收的数据长度

```
Syntax : public int getLength()
```

1.  **setData() :** 用于设置该数据包的数据。

```
Syntax : public void setData(byte[] buf,
           int offset,
           int length)
Parameters :
buf : data buffer
offset :offset into the data
length : length of the data
```

```
Syntax : public void setData(byte[] buf)
Parameters :
buf : data buffer
```

1.  **setAddress() :** 用于设置此数据包发送到的地址。

```
Syntax : public void setAddress(InetAddress iaddr)
Parameters : 
iaddr : InetAddress of the recipient
```

1.  **设置端口():**设置目的地接收该数据包的端口。

```
Syntax :public void setPort(int iport)
Parameters : 
iport : the port number
```

1.  **setSocketAddress() :** 用于设置目的地的套接字地址(IP 地址+端口号)。

```
Syntax : public void setSocketAddress(SocketAddress address)
Parameters :
address : socket address
```

1.  **getSocketAddress() :** 返回此数据包的套接字地址。如果收到，返回主机的套接字地址。

```
Syntax : public SocketAddress getSocketAddress()
```

1.  **设置长度():**用于设置此数据包的长度。

```
Syntax :public void setLength(int length)
Parameters :
length : length of the packet
```

**Java 实现:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
//Java program to illustrate various
//DatagramPacket class methods
import java.io.IOException;
import java.net.DatagramPacket;
import java.net.InetAddress;
import java.util.Arrays;

public class datapacket
{
    public static void main(String[] args) throws IOException
    {

        byte ar[] = { 12, 13, 15, 16 };
        byte buf[] = { 15, 16, 17, 18, 19 };
        InetAddress ip = InetAddress.getByName("localhost");

        // DatagramPacket for sending the data
        DatagramPacket dp1 = new DatagramPacket(ar, 4, ip, 1052);

        // setAddress() method
        // I have used same address as in initiation
        dp1.setAddress(ip);

        // getAddress() method
        System.out.println("Address : " + dp1.getAddress());

        // setPort() method
        dp1.setPort(2525);

        // getPort() method
        System.out.println("Port : " + dp1.getPort());

        // setLength() method
        dp1.setLength(4);

        // getLength() method
        System.out.println("Length : " + dp1.getLength());

        // setData() method
        dp1.setData(buf);

        // getData() method
        System.out.println("Data : " + Arrays.toString(dp1.getData()));

        // setSocketAddress() method
        //dp1.setSocketAddress(address.getLocalSocketAddress());

        // getSocketAddress() method
        System.out.println("Socket Address : " + dp1.getSocketAddress());

        // getOffset() method
        System.out.println("Offset : " + dp1.getOffset());

    }
}
```

**输出:**

```
Address : localhost/127.0.0.1
Port : 2525
Length : 4
Data : [15, 16, 17, 18, 19]
Socket Address : localhost/127.0.0.1:2525
Offset : 0
```

有关使用数据报套接字通过网络发送实际数据包的客户端-服务器程序的详细实现，请参考–[使用 UDP 数据报套接字](https://www.geeksforgeeks.org/working-udp-datagramsockets-java/)
**参考:**
[官方 Java 文档](https://docs.oracle.com/javase/7/docs/api/java/net/DatagramPacket.html)
本文由 **Rishabh Mahrsee** 提供。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。