# 在 Java 中查找一个 URL 的 IP 地址

> 原文:[https://www . geesforgeks . org/find-IP-address-of-a-URL-in-Java/](https://www.geeksforgeeks.org/finding-ip-address-of-a-url-in-java/)

先决条件:[InetAddress](https://www.geeksforgeeks.org/networking-class-in-java/)
**getByName():**返回给定主机的 InetAddress。如果主机是一个字面上的 IP 地址，那么只检查其有效性。获取指定主机的公共 IP 地址。它以主机为参数，返回相应的 IP 地址。

**示例:**

```java
Input : www.google.com
Output : 216.58.199.164

Input : localhost
Output : 127.0.0.1
```

下面的程序说明了如何获取公共 IP 地址:

**注意:**这些程序不会在在线编译器上运行。改用像 Netbeans、Eclipse 等离线编译器。

**程序 1:** 获取任意网址的 IP 地址

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// how to fetch public IP Address
import java.net.*;
import java.*;

class GFG {
    public static void main(String args[])
        throws UnknownHostException
    {
        // The URL for which IP address needs to be fetched
        String s = "https:// www.google.com/";

        try {
            // Fetch IP address by getByName()
            InetAddress ip = InetAddress.getByName(new URL(s)
                                                       .getHost());

            // Print the IP address
            System.out.println("Public IP Address of: " + ip);
        }
        catch (MalformedURLException e) {
            // It means the URL is invalid
            System.out.println("Invalid URL");
        }
    }
}
```

**输出:**

```java
Public IP Address of: www.google.com/216.58.196.164
```

**程序二:**获取自己系统的公共 IP 地址
要查找公共 IP，使用[http://bot.whatismyipaddress.com](http://bot.whatismyipaddress.com)。这是一个在线工具，可以找到系统的公共知识产权。打开网址，读一行，打印出来。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// how to fetch public IP Address
import java.net.*;
import java.*;

class GFG {
    public static void main(String args[])
        throws UnknownHostException
    {
        String systemipaddress = "";
        try {
            URL url_name = new URL("http://bot.whatismyipaddress.com");

            BufferedReader sc = new BufferedReader(
                new InputStreamReader(url_name.openStream()));

            // reads system IPAddress
            systemipaddress = sc.readLine().trim();
        }
        catch (Exception e) {
            systemipaddress = "Cannot Execute Properly";
        }
        // Print IP address
        System.out.println("Public IP Address: "
                           + systemipaddress + "\n");
    }
}
```

**输出:**

```java
Public IP Address: 103.62.239.242
```