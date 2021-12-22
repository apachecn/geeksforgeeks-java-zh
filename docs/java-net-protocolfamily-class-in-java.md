# java 中的 java.net.ProtocolFamily 类

> 原文:[https://www . geesforgeks . org/Java-net-protocol family-class-in-Java/](https://www.geeksforgeeks.org/java-net-protocolfamily-class-in-java/)

ProtocolFamily 是一个 java 接口。 **java.net.ProtocolFamily** 代表了一个通信协议家族。**Java . net . standard ProtocolFamily**实现 ProtocolFamily 接口。

```java
public interface ProtocolFamily 
```

### **Java . net . protocol family 的方法**

**java.net.ProtocolFamily** 界面只包含一个方法:

<figure class="table">

| s。没有。 | way | explain | Return type |
| --- | --- | --- | --- |
| 1。 | 名称() | The name () method returns the name of the protocol family. | 线 |

</figure>

### **使用协议家族接口**

<figure class="table">

| 没有。 | 包裹 | 修饰符和类型 | 名字 | 描述 |
| --- | --- | --- | --- | --- |
| 1. | java.net | 班级 | 标准协议家庭 | 标准协议类定义了通信协议的标准系列。 |
| 2. | java.nio.channels | 静态数据图表通道 | 打开(ProtocolFamily 家族) | 方法打开一个数据报通道。 |
| 3. | java.nio.channels.spi | 抽象数据图表通道 | selector provider . OpenDataGramChannel(ProtocolFamily 家族) | 打开数据报通道。 |

</figure>

**更好理解 ProtocolFamily 接口的 Java 程序**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to get Protocol
// family for an IP Address

// import Guava library
import com.google.common.net.InetAddresses;
import java.io.*;
import java.net.*;

class GFG {
    public static void main(String[] args)
    {
        try {
            // to get the ip address of
            InetAddress ip
                = InetAddress.getByName("45.22.30.39");
            System.out.println("Host Name is "
                               + ip.getHostName());

            // getProtocolFamily() will check and return the
            // protocol family of the given IP
            ProtocolFamily protocolFamily
                = getProtocolFamily(ip);

            System.out.println("Protocol family of the "
                               + ip.getHostName() + " is "
                               + protocolFamily);
        }
        catch (Exception e) {
            System.out.println("Some exception"
                               + e.getMessage());
        }
    }

    public static ProtocolFamily
    getProtocolFamily(InetAddress inetAddress)
    {
        // to check if address is valid or not
        if (InetAddresses.isInetAddress(
                inetAddress.getHostName())) {
            // if address is valid
            // will return the protocol family of the
            // address
            return StandardProtocolFamily.INET;
        }
        else {
            // address is not valid
            System.out.println(
                "Address " + inetAddress
                + "is invalid hence can't determine the protocol family");
        }
        return StandardProtocolFamily.INET;
    }
}
```

**Output**

```java
Host Name is 45.22.30.39
Protocol family of the 45.22.30.39 is INET
```