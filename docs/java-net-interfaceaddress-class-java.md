# Java 中的 Java.net.InterfaceAddress 类

> 原文:[https://www . geesforgeks . org/Java-net-interface address-class-Java/](https://www.geeksforgeeks.org/java-net-interfaceaddress-class-java/)

这个类代表一个网络接口地址。每个有 IP 地址的设备在网络接口上都有一个 IP 地址。事实上，ping 命令不是 ping 一个设备，而是设备接口地址。Java 提供了一些处理接口地址的方法，可以用在需要知道网络拓扑的地方，用于网络中的故障检测等。
**方法:**

1.  **getAddress() :** 返回该地址的 InetAddress。

```java
Syntax : public InetAddress getAddress()
```

1.  **getBroadcast() :** 返回该接口地址的广播地址的 InetAddress。由于只有 IPv4 地址有广播地址，使用 IPv6 地址时将返回空值。

```java
Syntax :public InetAddress getBroadcast()
```

1.  **getNetworkPrefixLength():**返回该接口地址的前缀长度，即该地址的子网掩码。

```java
Syntax :public short getNetworkPrefixLength()
```

1.  **等于():**用于指定对象与该接口地址的比较。仅当给定对象不为空并且表示与此对象相同的接口地址时，才返回 true。

```java
Syntax :public boolean equals(Object obj)
Parameters :
obj : obj to compare with
```

1.  **hashCode() :** 返回该接口地址的 hashCode。

```java
Syntax :public int hashCode()
```

1.  **toString() :** 返回此接口地址的字符串表示形式。该字符串的形式为:接口地址/前缀长度。

```java
Syntax :public String toString()
```

**Java 实现:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to illustrate methods of
// Java.net.InterfaceAddress class
import java.net.InterfaceAddress;
import java.net.NetworkInterface;
import java.net.SocketException;
import java.util.List;

public class interfaceaddress
{
    public static void main(String[] args) throws SocketException
    {
        // Modify according to your system
        NetworkInterface nif = NetworkInterface.getByIndex(1);
        List<InterfaceAddress> list = nif.getInterfaceAddresses();

        for (InterfaceAddress iaddr : list)
        {

            // getAddress() method
            System.out.println("getAddress() : " + iaddr.getAddress());

            // getBroadcast() method
            System.out.println("getBroadcast() : " + iaddr.getBroadcast());

            // getNetworkPrefixLength() method
            System.out.println("PrefixLength : " + iaddr.getNetworkPrefixLength());

            // hashCode() method
            System.out.println("Hashcode : " + iaddr.hashCode());

            // toString() method
            System.out.println("toString() : " + iaddr.toString());

            System.out.println("--------------------\n");
        }
    }

}
```

**输出:**

```java
getAddress() : /127.0.0.1
getBroadcast() : /127.255.255.255
PrefixLength : 8
Hashcode : -16777208
toString() : /127.0.0.1/8 [/127.255.255.255]
--------------------

getAddress() : /0:0:0:0:0:0:0:1
getBroadcast() : null
PrefixLength : 128
Hashcode : 129
toString() : /0:0:0:0:0:0:0:1/128 [null]
--------------------
```

请修改上述程序中 getbyIndex()方法中的索引，因为索引 1 处的网络接口在您的系统中可能为空。关于这个方法的更多细节，请参考- [java.net.NetworkInterface 类](https://write.geeksforgeeks.org/java-net-networkinterface-class-in-java/)
**参考文献:**
[官方 java 文档](https://docs.oracle.com/javase/7/docs/api/java/net/InterfaceAddress.html)
本文由 **Rishabh Mahrsee** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。