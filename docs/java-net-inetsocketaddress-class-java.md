# Java 中的 Java.net.InetSocketAddress 类

> 原文:[https://www . geesforgeks . org/Java-net-inetsocketaddress-class-Java/](https://www.geeksforgeeks.org/java-net-inetsocketaddress-class-java/)

这个类实现了 IP 套接字地址(IP 地址和端口号的组合)。这个类的对象是不可变的，可以用于绑定、连接的目的。

**施工人员:**

**1。InetSocketAddress(InetAddress addr，int port) :** 这个构造函数类似于套接字地址的一般结构，具有 Inet 地址和端口号的属性。

```
Syntax :public InetSocketAddress(InetAddress addr,
                 int port)
Parameters :
addr : IP address
port : port number
```

**2。InetSocketAddress(内部端口):**使用指定的端口号和通配符 IP 地址创建 SocketAddress 对象。通配符 IP 地址的值为 0.0.0.0，它将您的套接字绑定到所有网卡。

```
Syntax : public InetSocketAddress(int port)
Parameters :
port : port number
```

**3。InetSocketAddress(字符串主机名，int 端口):**创建 SocketAddress 对象，并将其绑定到指定的端口和主机。主机名解析是为了找到用于绑定目的的 IP 地址，而不是主机名。如果解析返回 null，该地址将被标记为未解析。

```
Syntax : public InetSocketAddress(String hostname,
                 int port)
Parameters :
hostname :  host name
port : port number
```

**方法:**

**1。createUnresolved() :** 使用给定的主机和端口号创建套接字地址，其中不尝试解析主机名，并且该地址被标记为未解析。

```
Syntax :public static InetSocketAddress createUnresolved(String host,
                                 int port)
Parameters :
host : host name
port : port number
```

**2。getPort() :** 返回这个套接字地址的端口号。

```
Syntax : public final int getPort()
```

**3。getAddress() :** 返回这个套接字地址的 IP 地址。

```
Syntax : public final InetAddress getAddress()
```

**4。getHostName() :** 返回主机名，如果是使用 IP 地址创建的，则使用反向查找。

```
Syntax : public final String getHostName()
```

**5。getHostString() :** 如果使用主机名或用于创建的地址文字的字符串表示形式创建，则返回主机名。

```
Syntax : public final String getHostString()
```

**6。isUnresolved() :** 返回一个布尔值，指示该地址是否被解析。

```
Syntax : public final boolean isUnresolved()
```

**7。toString() :** 返回此 InetSocket 地址对象的字符串表示形式。首先在 InetAddress 部分调用 toString()方法，然后在冒号后追加端口号。

```
Syntax : public String toString()
```

**8。equals() :** 比较此 socketaddress 对象是否等于指定对象。如果两者表示相同的地址和端口号，或者在地址未解析的情况下表示主机名和端口号，则两者相等。

```
Syntax : public final boolean equals(Object obj)
Parameters :
obj : object to compare with
```

**9。hashcode() :** 返回这个 InetSocketAddress 对象的 hashcode。

```
Syntax : public final int hashCode()
```

**Java 实现:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to illustrate various
// InetSocketAddress class
import java.net.InetAddress;
import java.net.InetSocketAddress;
import java.net.UnknownHostException;

public class InetsockAddress
{

    public static void main(String[] args) throws UnknownHostException
    {

        // Following constructor can be used to create InetSocketAddress
        // objects.
        InetSocketAddress isa1 = new InetSocketAddress(5500);
        InetSocketAddress isa2 = new InetSocketAddress("localhost", 5050);
        InetAddress ip = InetAddress.getByName("localhost");
        InetSocketAddress isa3 = new InetSocketAddress(ip, 8800);

        // createUnresolved() does not attempt to resolve the hostname.
        InetSocketAddress isa4 = InetSocketAddress.createUnresolved("abc", 5055);

        // These InetSocketAddress objects can be used to create sockets
        // in socket programming, in place of specifying individually the IP
        // address and port number. Please refer to TCP articles for their
        // further use.

        // These can also be used to retrieve information about the
        // socketAddress objects.

        // getHostName() method
        System.out.println("Hostname : " + isa1.getHostName());

        // getHostString() method
        System.out.println("Host string : " + isa1.getHostString());

        // getAddress() method
        System.out.println("Inet address : " + isa1.getAddress());

        // getPort() method
        System.out.println("Port : " + isa1.getPort());

        // isUnresolved() method
        System.out.println("isUnresolved : " + isa1.isUnresolved());

        // equals() method
        System.out.println("isa1==isa2 : " + isa1.equals(isa2));

        // toString() method
        System.out.println("toString : " + isa1.toString());

        // hashCode() method
        System.out.println("hashCode : " + isa1.hashCode());
    }

}
```

**输出:**

```
Hostname : 0.0.0.0
Host string : 0.0.0.0
Inet address : 0.0.0.0/0.0.0.0
Port : 5500
isUnresolved : false
isa1==isa2 : false
toString : 0.0.0.0/0.0.0.0:5500
hashCode : 5500
```

参考文献:
[Java 官方文档](https://docs.oracle.com/javase/7/docs/api/java/net/InetSocketAddress.html)
本文由**里沙布·马尔塞**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。