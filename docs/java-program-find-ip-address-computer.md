# Java 程序查找你电脑的 IP 地址

> 原文:[https://www . geesforgeks . org/Java-program-find-IP-address-computer/](https://www.geeksforgeeks.org/java-program-find-ip-address-computer/)

**IP(互联网协议)地址**是分配给连接到 TCP/IP 网络的每台计算机和另一个设备(例如，路由器、移动设备等)的标识符，用于定位和识别与网络上其他节点通信的节点。IP 地址通常以人类可读的符号书写和显示，例如 IPv4(32 位 IP 地址)中的 192.168.1.35。

IP 地址有两个主要功能:主机或网络接口识别和本地寻址。它的作用被描述如下:“一个名字表明我们寻求什么。地址表明它在哪里。一条路线指示如何到达那里。”

先决条件:[Java 中的联网| Set 1 (InetAddress 类)](https://www.geeksforgeeks.org/networking-class-in-java/)，[Java 中的 trim()](https://www.geeksforgeeks.org/trim-remove-leading-trailing-spaces-string-java/)。
InetAddress.getLocalHost()用于查找局域网或任何其他本地网络中使用的**私有 IP** 地址。

要找到 [**公共 IP**](https://en.wikipedia.org/wiki/IP_address#Public_address) ，我们使用(一个在线工具找到你的公共 IP)，我们打开网址，读一行，打印一行。

下面是上述步骤的 Java 实现。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to find IP address of your computer
// java.net.InetAddress class provides method to get
// IP of any host name
import java.net.*;
import java.io.*;
import java.util.*;
import java.net.InetAddress;

public class JavaProgram
{
    public static void main(String args[]) throws Exception
    {
        // Returns the instance of InetAddress containing
        // local host name and address
        InetAddress localhost = InetAddress.getLocalHost();
        System.out.println("System IP Address : " +
                      (localhost.getHostAddress()).trim());

        // Find public IP address
        String systemipaddress = "";
        try
        {
            URL url_name = new URL("http://bot.whatismyipaddress.com");

            BufferedReader sc =
            new BufferedReader(new InputStreamReader(url_name.openStream()));

            // reads system IPAddress
            systemipaddress = sc.readLine().trim();
        }
        catch (Exception e)
        {
            systemipaddress = "Cannot Execute Properly";
        }
        System.out.println("Public IP Address: " + systemipaddress +"\n");
    }
}
```

**输出:**

```java
 System IP Address : 10.0.8.204
 Public IP Address : 35.166.48.97
```

**注:**以上输出是 GeeksforGeeks 在线编译器使用的机器，[ide.geeksforgeeks.org](https://ide.geeksforgeeks.org/)

本文由**普拉莫德·库马尔**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。