# java 中的 java.net.Socket 类

> 原文:[https://www . geesforgeks . org/Java-net-socket-in-Java 类/](https://www.geeksforgeeks.org/java-net-socket-class-in-java/)

java.net.Socket 类允许我们创建套接字对象，帮助我们实现所有基本的套接字操作。我们可以执行各种网络操作，如发送、读取数据和关闭连接。使用 with java.net.Socket 类创建的每个 Socket 对象都与一个远程主机完全关联，为了连接到另一个不同的主机，我们必须创建一个新的 Socket 对象。

从 java.net 包导入套接字类的语法:

> **导入 Java . net . socket；**

**Socket 类使用的方法:**

<figure class="table">

| **方法** | **描述** |
| --- | --- |
| 绑定(SocketAddress 绑定点) | 此方法用于将套接字绑定到本地地址。 |
| 关闭() | 此方法用于终止套接字。 |
| 连接(套接字地址端点) | 此方法用于将套接字连接到服务器。 |
| getChannel（） | 此方法返回与套接字关联的对象(如果有)。 |
| getInetAddress() | 此方法返回套接字连接到的地址。 |
| getInputStream() | 此方法返回套接字的输入流。 |
| getKeepAlive() | 此方法用于检查 SO_KEEPALIVE 是否启用。 |
| getLocalAddress() | 此方法用于获取套接字绑定到的本地地址。 |
| getLocalPort() | 此方法返回套接字绑定到的本地地址。 |
| getLocalSocketAddress() | 此方法返回套接字绑定的端点。 |
| getOOBInline() | 此方法检查 SO _ OOBINLINE 是否已启用。 |
| getOutputStream() | 此方法返回套接字的输出流。 |
| getPort（） | 此方法返回与套接字关联的远程端口号。 |
| getReceiveBufferSize() | 此方法用于为套接字获取 SO_RCVBUF 选项的值，该值是平台在套接字上用作输入的缓冲区大小。 |
| getRemoteSocketAddress() | 这个方法返回套接字的端点地址，如果没有连接，则返回 null。 |
| getReuseAddress() | 此方法检查是否启用了重用 ADDR。 |
| getSendBufferSize() | 此方法用于获取套接字的 SO_SNDBUF 选项的值，该值用作套接字上平台输出的缓冲区大小。 |
| getSoLinger() | 此方法返回 SO_LINGER 的设置 |
| getSoTimeout() | 此方法返回 S0 _ 超时的设置 |
| getTcpNoDelay() | 此方法用于测试 TCP_NODELAY 是否启用。 |
| getTrafficClass() | 此方法获取从该套接字发送的数据包的 IP 报头中的流量类或服务类型。 |
| isBound() | 此方法返回套接字的绑定状态 |
| isClosed() | 此方法返回套接字的关闭状态。 |
| isConnected() | 此方法返回套接字的连接状态。 |
| is put 关机() | 此方法返回套接字连接的读半部分是否关闭 |
| isOutputShutdown() | 此方法返回套接字连接的写半部分是否关闭。 |
| int data(内部数据) | 这个方法在套接字上发送一个字节的紧急数据 |
| setKeepAlive(boolean on) | 此方法启用/禁用 SO_KEEPALIVE |
| setOOBInline(布尔开) | 此方法启用/禁用 SO_OOBINLINE(接收 TCP 紧急数据)默认情况下，此选项处于禁用状态，在套接字上接收的 TCP 紧急数据将被静默丢弃。 |
| 设置性能首选项(内部连接时间、内部延迟、内部带宽) | 此方法设置此套接字的性能首选项。 |
| setreceivbuffersize(int size) | 此方法将 SO_RCVBUF 选项设置为此套接字指定的值。 |
| setReuseAddress(boolean on | 此方法启用/禁用 SO_REUSEADDR 套接字选项 |
| setSendBufferSize(int size) | 此方法将 SO_SNDBUF 选项设置为此套接字指定的值 |
| setsxmlsocket implfactory(socket implfactory fac) | 此方法为应用程序设置客户端套接字实现工厂。 |
| setSoLinger(boolean on，int linger) | 此方法启用/禁用指定停留时间(秒)的 SO_LINGER。 |
| set time out(内部超时) | 此方法启用/禁用指定超时的 SO_TIMEOUT，以毫秒为单位。 |
| setTcpNoDelay(布尔值开 | 此方法启用/禁用 TCP_NODELAY(禁用/启用 Nagle 算法)。 |
| settraficclass(int TC) | 此方法为从此套接字发送的数据包在 IP 报头中设置流量类别或服务类型八位字节。 |
| shutdownInput() | 这个方法将这个套接字的输入流放在“流的末尾”。 |
| toString() | 此方法将套接字转换为字符串。 |

</figure>

**插座类应用:**

**1。**套接字类是在创建流套接字时实现的，它连接到指定的端口号和端口地址。

> 公共套接字(内部地址，内部端口)

**2。** Socket 类用于创建 Socket，并连接到 javax.net 指定远程端口上的指定远程地址

> **socket factory . createsocket(InetAddress 地址，int port，InetAddress localAddress，int localPort)**

****3。**在 javax.ssl.net，Socket 类用于返回在给定端口连接到命名主机的现有套接字上分层的套接字。**

> ****sslsocketfactory . createsocket(套接字 s，字符串主机，int 端口，布尔 autoClose)****

****4。**在 javax.rmi.ssl 中，Socket 类用于创建一个 ssl 套接字。**

> ****ssrmicrosoftfactory . create xmlsocket(string host，int port)****

****5。**在 java.nio.channels 中，Socket 类用于检索与其通道相关联的套接字**

> ****SocketChannel.socket()****

****套接字类实现的 Java 示例:****

****1。服务器端:****

## **Java 语言(一种计算机语言，尤用于创建网站)**

```java
import java.io.*;
import java.net.*;
public class MyServer {
    public static void main(String[] args)
    {
        try {
            ServerSocket ss = new ServerSocket(6666);

            // establishes connection
            Socket soc = ss.accept();

            // invoking input stream
            DataInputStream dis
                = new DataInputStream(s.getInputStream());

            String str = (String)dis.readUTF();

            System.out.println("message= " + str);

            // closing socket
            ss.close();

        } // for catching Exception in run time
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

****客户端输出:****

**![](img/aba707e4a7d4d5a28e48cf6c82dd3ba1.png)**

****2。客户端:****

## **Java 语言(一种计算机语言，尤用于创建网站)**

```java
import java.io.*;
import java.net.*;
public class MyClient {
    public static void main(String[] args)
    {
        try {

            // initializing Socket
            Socket soc = new Socket("localhost", 6666);

            DataOutputStream d = new DataOutputStream(
                soc.getOutputStream());

            // message to display
            d.writeUTF("Hello GFG Readers!");         

            d.flush();

            // closing DataOutputStream
            d.close();

            // closing socket
            soc.close();
        }

        // to initialize Exception in run time
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

****服务器输出:****

**![](img/c9f35c0776c3fc96acd03e5fb7df52a8.png)**