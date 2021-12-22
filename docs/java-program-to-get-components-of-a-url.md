# 获取网址组件的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-program-to-get-components-of-a-URL/](https://www.geeksforgeeks.org/java-program-to-get-components-of-a-url/)

**Java 联网:**由于 Java 程序被编写为跨多个开发环境**执行，因此多个设备意味着远程位置的计算机。因此，这两个设备可以在相同的位置进行通信，也可以在与某个网络连接的不同位置进行通信。对于 java 网络，需要使用“net”包。它适用于两种不同的协议，即 TCP 和 UDP。TCP 在 java 中是首选的，因为它是一个面向连接的协议，而 UDP 是一个无连接的协议。因此，可靠性不如 UDP。**

*   代表传输控制协议
*   代表用户数据报协议

**概念:** URL 类和内置[T3】getProtocol()方法 T5】](https://www.geeksforgeeks.org/url-getprotocol-method-in-java-with-examples/)

[URL 类](https://www.geeksforgeeks.org/url-class-java-examples/)是一个统一资源定位器，它指向万维网上的一个资源。

**语法:**用于导入网址类:

```java
import java.util.net ;
```

[*getProtocol()*](https://www.geeksforgeeks.org/url-getprotocol-method-in-java-with-examples/)***getProtocol()*功能是 [URL 类](https://www.geeksforgeeks.org/url-class-java-examples/) 的一部分。函数 getProtocol()返回指定网址的协议。**

****功能签名:****

```java
**public String getProtocol() ;**
```

****语法:****

```java
**url.getProtocol();**
```

****参数:**该功能不需要任何参数**

****返回类型:**函数返回**字符串**类型**

****图解:**现在，通过图解进一步了解 URL 类的内部工作原理:**

> **考虑随机网址:**
> 
> **在这里，**
> 
>  **使用的协议:http
> 
> 主机名:www.geeksforgeeks.com
> 
> 路径是文件访问:javaexamples/net _ single user . htm
> 
> 端口号:443**

**这里使用的是 HTTP 协议，因为从URL 本身的名称就可以很容易看出。**

**java.net.URL 类表示一个 URL。有构造函数来生成新的网址，也有方法来解析网址的各个部分。然而，这个类别的核心是允许你从一个网址上强制输入流的方法，这样你就可以从服务器上读取数据。**

**URL 类与协议和内容处理程序紧密相关。目的是将正在下载的信息与用于下载的协议分开。协议处理程序负责与服务器通信，即从服务器向客户端移动字节。它处理与服务器和任何头的任何必要的协商。它的工作是只返回请求的数据或文件的实际字节。内容处理程序获取这些字节，并将它们转换成一些非常简单的 Java 对象，如 InputStream 或 ImageProducer。**

****网址的组成部分:**网址可以有多种形式。然而最普遍的是遵循一个三要素系统-**

1.  **协议:这里的协议是 HTTP**
2.  **主机名:主机系统的名称。**
3.  **文件名:系统上文件的路径名。**
4.  **端口号:要连接的端口号(通常是可选的)。**

****实现:**下面是获取网址各部分的 java 代码:**

## **Java 语言(一种计算机语言，尤用于创建网站)**

```java
**// Java Program to Get Components of a URL

import java.util.*;
// Importing URL class
import java.net.URL;

public class GFG {
    // Main driver method
    public static void main(String[] args) throws Exception
    {
        // Making object of URL type
        // URL url = new URL(args[0]);

        // Url taken for consideration as input URL
        URL url = new URL(
            "https://www.geeksforgeeks.com/javaexamples/net_singleuser.htm");

        // Print the string representation of the URL.
        System.out.println("URL is:" + url.toString());

        // Retrieve the protocol of URL
        System.out.println("protocol is: "
                           + url.getProtocol());

        // Retrieve the filename of URL
        System.out.println("file name is: "
                           + url.getFile());

        // Retrieve the hostname of URL
        System.out.println("host is: " + url.getHost());

        // Retrieve the path of URL
        System.out.println("path is: " + url.getPath());

        // Retrieve the port of URL
        System.out.println("port is: " + url.getPort());
        System.out.println("default port is: "
                           + url.getDefaultPort());
    }
}**
```

****Output**

```java
URL is:https://www.geeksforgeeks.com/javaexamples/net_singleuser.htm
protocol is: https
file name is: /javaexamples/net_singleuser.htm
host is: www.geeksforgeeks.com
path is: /javaexamples/net_singleuser.htm
port is: -1
default port is: 443
```**