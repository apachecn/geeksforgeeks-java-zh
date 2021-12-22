# Java 中的 Java.net.Inet4Address 类

> 原文:[https://www . geesforgeks . org/Java-net-inet 4 address-class-Java/](https://www.geeksforgeeks.org/java-net-inet4address-class-java/)

这个类扩展了 InetAddress 类，表示一个 IPv4 地址。它提供了解释和显示关于 IP 地址的有用信息的方法。

**这个类的方法采用 4 种格式输入:**

1.  **D.D.D.D.:** When this format is used as input, each given value is assigned to 4 bytes of the IP address from left to right.
2.  **D.D.D.:** When this format is used as input, the last part is interpreted as a 16-bit number and assigned to the rightmost 2 bytes as the host address. This is usually used to specify a class B address.
3.  **D.D.:** When this format is used as input, the last part is interpreted as a 24-digit number and assigned to the rightmost 3 bytes as the host address. This is usually used to specify a class A address.
4.  **D:** When this format is used as input, the given value is directly stored as the network address without any rearrangement.

**方法:**

<figure class="table">

| way | Description |
| --- | --- |
| equals (objectobj) | This method compares this object with the specified object. |
| getaddress () | This method returns the original IP address of this InetAddress object. |
| GetHostAddress () | This method returns the IP address string in the form of text presentation. |
| hashCode () | This method returns the Hashcode of this IP address. |
| isani local address () | This method utility routinely checks whether InetAddress is a wildcard address. |
| Islinklocaladdress () | This method utility routinely checks whether InetAddress is a link local address. |
| ISloopback address () | This method utility routinely checks whether InetAddress is a loopback address. |
| ISMC Global () | This method utility routinely checks whether the multicast address has global scope. |
| Ismaclenglocal () | This method utility routinely checks whether the multicast address has a link range. |
| ismcnodellocal () | This method utility routine checks whether the multicast address has a node range. |
| ismcorglobal () | This method utility routine checks whether the multicast address has an organization range. |
| ismcsitelocal () | This method utility routinely checks whether the multicast address has a site range. |
| IS Multicast Address () | This method utility routinely checks whether InetAddress is an IP multicast address. |
| Issitelocaladdress () | This method utility routinely checks whether InetAddress is the local address of the site. |

</figure>

**Java 实现:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to illustrate various
// Inet4Address class methods
import java.net.Inet4Address;
import java.net.InetAddress;
import java.net.UnknownHostException;
import java.util.Arrays;

public class inet4add
{
    public static void main(String args[]) throws UnknownHostException
    {
        String url = "www.geeksforgeeks.org";
        Inet4Address ip1 = (Inet4Address) Inet4Address.getByName(url);
        Inet4Address ip2 = (Inet4Address) InetAddress.getByName("www.yahoo.com");

        // Following methods checks the property of the thus created object.
        // getAddress() method
        System.out.println("Address : " + Arrays.toString(ip1.getAddress()));

        // getHostAddress() method
        System.out.println("Host Address : " + ip1.getHostAddress());

        // isAnyLocalAddress() method
        System.out.println("isAnyLocalAddress : " + ip1.isAnyLocalAddress());

        // isLinkLocalAddress() method
        System.out.println("isLinkLocalAddress : " + ip1.isLinkLocalAddress());

        // isLoopbackAddress() method
        System.out.println("isLoopbackAddress : " + ip1.isLoopbackAddress());

        // isMCGlobal() method
        System.out.println("isMCGlobal : " + ip1.isMCGlobal());

        // isMCLinkLocal() method
        System.out.println("isMCLinkLocal : " + ip1.isMCLinkLocal());

        // isMCNodeLocal() method
        System.out.println("isMCNodeLocal : " + ip1.isMCNodeLocal());

        // isMCOrgLocal() method
        System.out.println("isMCOrgLocal : " + ip1.isMCOrgLocal());

        // isMCSiteLocal() method
        System.out.println("isMCSiteLocal : " + ip1.isMCSiteLocal());

        // isMulticastAddress() method
        System.out.println("isMulticastAddress : " + ip1.isMulticastAddress());

        // isSiteLocalAddress() method
        System.out.println("isSiteLocalAddress : " + ip1.isSiteLocalAddress());

        // hashCode() method
        System.out.println("hashCode : " + ip1.hashCode());

        // equals() method
        System.out.println("ip1==ip2 : " + ip1.equals(ip2));
    }
}
```

**输出:**

```
Address : [52, 84, 102, -116]
Host Address : 52.84.102.140
isAnyLocalAddress : false
isLinkLocalAddress : false
isLoopbackAddress : false
isMCGlobal : false
isMCLinkLocal : false
isMCNodeLocal : false
isMCOrgLocal : false
isMCSiteLocal : false
isMulticastAddress : false
isSiteLocalAddress : false
hashCode : 877946508
ip1==ip2 : false
```

本文由**里沙布·马赫塞**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。