# 确定本地计算机在 Java 中的 IP 地址&主机名

> 原文:[https://www . geesforgeks . org/确定 java 中本地计算机的 ip 地址主机名/](https://www.geeksforgeeks.org/determining-the-ip-address-hostname-of-local-computer-in-java/)

[**IP 地址**](https://en.wikipedia.org/wiki/IP_address) 代表**互联网协议地址**，是一个数字标签，它被唯一地分配给使用互联网协议的计算机网络中连接的每个设备。一个 IP 地址有两个主要功能:

1.  它标识主机，或者更具体地说，标识其网络接口。
2.  它提供了主机在网络中的位置，因此能够建立到该主机的路径。

IP 地址还指定了路由器和终端系统之间发送和接收的数据包的格式。IP 地址空间由互联网分配号码管理局(IANA)在全球范围内进行管理，并由五个区域互联网注册管理机构在其指定区域内负责分配给本地互联网注册管理机构，如互联网服务提供商和其他最终用户。

**IP 版本:**

如今，在互联网寻址中最常见的是两种版本的 IP 地址。它们是 IPv4 和 IPv6。

*   **IPv4:** IPv4 的大小为 32 位，即使用 IPv4 可以分配 4，294，967，296 个地址。IPv4 地址以点-十进制表示法表示，由 4 个用点分隔的十进制数字组成，每个数字的范围从 0 到 255。每个部分代表一组 8 位(一个八位字节)的地址。**即** 192.168.0.118
*   **IPv6:** 在 IPv6 中，地址大小从 IPv4 中的 32 位增加到 128 位，因此最多可提供 2^128(大约 3.403×10^38)地址。**即** 2001:db8:0:1234:0:567:8:1

**主机名**

[**主机名**](https://en.wikipedia.org/wiki/Hostname) 是互联网上给设备起的名字。即主机名是在互联网上如何称呼设备(就像人的名字一样)。主机名可以是由单个单词或短语组成的简单名称，也可以是结构化的。**即**笔记本电脑-MRRIH5PC

Java.net 包提供了几个有用的类和接口来处理网络和互联网。任何本地计算机的 IP 地址和主机名都可以使用 java.net.InetAddress 类来确定。

java.net.InetAddress

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to determine the IP address
// and host name of local computer

import java.io.*;
import java.net.InetAddress;
public class GFG {
    public static void main(String[] args) throws Exception
    {
        // a variable of type InetAddress to store
        // the address of the local host
        InetAddress addr = InetAddress.getLocalHost();
        // Returns the IP address string in
        // textual presentation.
        System.out.println("Local HostAddress:  "
                           + addr.getHostAddress());
        // Gets the host name for this IP address.
        System.out.println("Local host name: "
                           + addr.getHostName());
    }
}
```

**Output**

```
Local HostAddress:  127.0.0.1
Local host name: localhost
```