# Java 中的 Java.net.MulticastSocket 类

> 原文:[https://www . geesforgeks . org/Java-net-multicast socket-class-Java/](https://www.geeksforgeeks.org/java-net-multicastsocket-class-java/)

此类用于发送和接收多播 IP 数据包。它扩展了 DatagramSocket 类，并为加入组提供了附加功能。所有加入该组的客户端都将收到发送到该组 IP 地址的消息。必须记住，为了向组发送数据包，数据报套接字不必加入该组，但是为了接收发往该组的数据包，它必须加入该组。这个类提供了多种方法来控制多播数据包的流量，如设置 ttl、使用的网络接口等，以及加入和离开组的主要功能。
**施工人员:**

*   **公共多播套接字():**创建多播套接字。当使用这个构造函数时，我们必须显式设置所有字段，如组地址、端口号等。

```
Syntax :public MulticastSocket() 
```

*   **公共多播套接字(int 端口):**创建绑定在指定端口上的多播套接字。

```
Syntax :public MulticastSocket(int port) 
Parameters : 
port : port number to bind this socket to
```

*   **公共多播套接字(SocketAddress bindaddr) :** 创建一个多播套接字，并将其绑定到指定的套接字地址。如果地址为空，则创建未绑定的套接字。

```
Syntax :public MulticastSocket(SocketAddress bindaddr) 
Parameters : 
bindaddr : Socket address to bind this socket to
```

**方法:**

*   **settl(已弃用):**用于设置从该组播套接字发送的数据包的生存时间，限制数据包的范围。此方法不推荐使用，因为它使用字节作为设置 TTL 的参数。setTimeToLive()用在它的位置。

```
Syntax :public void setTTL(byte ttl)
Parameters :
ttl : the time to live
```

*   **settitemolive():**该方法代替上述方法，因为它使用 int 值作为参数。指定的 ttl 必须在范围 0 < =ttl < =255 内，否则将引发 illegalArgumentException。

```
Syntax :public void setTimeToLive(int ttl)
Parameters :
ttl : the time to live
```

*   **getTTL(已弃用):**用于获取从该多播套接字发送的数据包的默认生存时间

```
Syntax :public byte getTTL()
```

*   **gettimeolive():**返回从该多播套接字发送的数据包的默认生存时间。

```
Syntax :public void getTimeToLive()
```

*   **joinGroup() :** 用于加入组播组。加入该组后，客户端将开始接收发送到该多播组地址的所有数据包。此方法接受要加入的组的地址。可以使用 setInterface()和 setNetworkInterface()方法对其行为进行进一步的更改。

```
Syntax :public void joinGroup(InetAddress mcastaddr)
               throws IOException
Parameters :
mcastaddr : multicast address to join
Throws :
IOException : if error occurs while joining or the address is
not a multicast address.
```

另一种重载方法，它还指定了加入组时要使用的网络接口。

```
Syntax :public void joinGroup(SocketAddress mcastaddr,
             NetworkInterface netIf)
               throws IOException
Parameters :
mcastaddr : multicast address to join
netIf : network interface to use while joining
Throws :
IOException : if error occurs while joining or the address is
not a multicast address.
```

*   **leaveGroup() :** 用于离开组播组。离开该组后，客户端将无法接收发往该组地址的数据包。

```
Syntax :public void leaveGroup(InetAddress mcastaddr)
               throws IOException
Parameters :
mcastaddr : multicast address to leave
Throws :
IOException : if error occurs while leaving
```

另一种用于离开组的重载方法，它也允许指定离开组的网络接口。

```
Syntax :public void leaveGroup(SocketAddress mcastaddr,
             NetworkInterface netIf)
               throws IOException
Parameters :
mcastaddr : multicast address to leave
netIf : network interface on which to leave
Throws :
IOException : if error occurs while leaving
```

*   **setInterface() :** 用于设置组播网络接口。

```
Syntax :public void setInterface(InetAddress inf)
                  throws SocketException
Parameters :
inf : the inetaddress
Throws :
SocketException : if error in underlying protocol
```

*   **getInterface() :** 返回用于组播数据包的网络接口。

```
Syntax :public InetAddress getInterface()
                         throws SocketException
Throws :
SocketException : if error in underlying protocol
```

*   **setNetworkInterface() :** 用于指定此套接字上传出数据包的网络接口。

```
Syntax :public void setNetworkInterface(NetworkInterface netIf)
                         throws SocketException
Parameters :
netIf : network interface to use
Throws :
SocketException : if error in underlying protocol
```

*   **getNetworkInterface() :** 返回此套接字上传出数据包的网络接口。

```
Syntax :public NetworkInterface getNetworkInterface()
                                     throws SocketException
Throws :
SocketException : if error in underlying protocol
```

*   **setLoopbackMode() :** 用于指定组播数据包是否会环回至本地套接字。

```
Syntax : public void setLoopbackMode(boolean disable)
                     throws SocketException
Parameters :
disable : true or false
```

*   **getLoopbackMode() :** 返回环回模式的设置。

```
Syntax : public vboolean getLoopbackMode()
                     throws SocketException
```

*   **send()(已弃用):**用于将数据包发送到组播组。它允许指定输出数据包的 ttl，而不是使用 setTimeToLive()方法指定的默认值。它不改变该值，但只对当前数据包使用指定的值。下面几行代码应该用来代替这个方法。
    int TTL = msock . gettimeolive()；
    msock . settitemolive(new TTL)；
    发送信息包；
    msock . settitemolive(TTL)；

```
Syntax :public void send(DatagramPacket p,
                   byte ttl)
          throws IOException
Parameters :
p : datagram packet to send
ttl : hte time to live
Throws :
IOException : If error occurs while setting the ttl
```

**Java 实现:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
//Java program to illustrate various
//MulticastSocket class methods
import java.io.IOException;
import java.net.InetAddress;
import java.net.MulticastSocket;
import java.net.NetworkInterface;
import java.util.Enumeration;

public class multisock
{
    public static void main(String[] args) throws IOException
    {

        MulticastSocket ms = new MulticastSocket();
        InetAddress ip = InetAddress.getByName("224.168.1.124");

        // setTTL() method
        // this method is deprecated and instead
        // use setTimeToLive() method
        // Un-commenting below line would throw
        // a warning as the method is deprecated
        ms.setTTL((byte) 25);

        // setTimeToLive() method, will override
        // setting by setTTL() method
        ms.setTimeToLive(20);

        // getTTL() method
        // deprecated, so use getTimeToLive() method instead
        System.out.println("TTL : " + ms.getTTL());

        // getTimeToLive() method
        System.out.println("Time to Live : " +
                             ms.getTimeToLive());

        NetworkInterface nif = NetworkInterface.getByIndex(1);
        Enumeration<InetAddress> enu = nif.getInetAddresses();
        InetAddress intadd = enu.nextElement();

        // setInterface() method
        ms.setInterface(intadd);

        // getInterface() method
        System.out.println("Interface : " + ms.getInterface());

        // setNetworkInterface() method
        ms.setNetworkInterface(nif);

        // getNetworkInterface() method
        System.out.println("Network Interface : " +
                           ms.getNetworkInterface());

        // setLoopbackMode() method
        ms.setLoopbackMode(true);

        // getLoopbackMode() method
        System.out.println("Loopback mode : " +
                            ms.getLoopbackMode());
    }

}
```

**输出:**

```
TTL : 20
Time to Live : 20
Interface : /127.0.0.1
Network Interface : name:lo (Software Loopback Interface 1)
Loopback mode : true
```

关于一个组播套接字应用程序的详细实现，方法是加入 Group()和发送()数据包，请参考[Java 中的一个群聊应用程序](https://www.geeksforgeeks.org/a-group-chat-application-in-java/)
**参考:**
[Java 官方文档](https://docs.oracle.com/javase/7/docs/api/java/net/MulticastSocket.html)
本文由 **Rishabh Mahrsee** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。