# java 中的 java.net.CacheRequest 类

> 原文:[https://www . geesforgeks . org/Java-net-cache request-class-in-Java/](https://www.geeksforgeeks.org/java-net-cacherequest-class-in-java/)

**CacheRequest** 类是在 java 中每当有需要的时候使用的，存储资源在 ***ResponseCache*** 中。更准确地说，这个类的实例为[输出流](https://www.geeksforgeeks.org/java-io-outputstream-class-java/)对象提供了将资源数据存储到缓存中的优势，事实上，这个输出流对象是由协议处理程序调用的。 **CacheRequest** 类属于[*java.net*](https://www.geeksforgeeks.org/java-net-urldecoder-class-java/)*包*以及其他类，如 Authenticator、CacheResponse、 [ServerSocket](https://www.geeksforgeeks.org/socket-programming-in-java/) 、 [SocketAddress](https://www.geeksforgeeks.org/java-net-inetsocketaddress-class-java/) 等等。

<figure class="table">T39】缓存响应T43】sockedadressT47】content handler

| Authenticator | Inet 6 address | Server socket |
| --- | --- | --- |
| Cache request | 互联网地址 | socket |
| inetsocketaddress |
| joggle/interface |

</figure>

java.Net 包是为 Java 提供网络基础设施的强大类的容器。现在，详述一下本课程中的两种方法，如下所示:

1.  [*Stop ()*](https://www.geeksforgeeks.org/understanding-exit-abort-and-assert/) *M* method
2.  *格体()*格体

**方法 1:** [*打掉()*](https://www.geeksforgeeks.org/understanding-exit-abort-and-assert/) 方法

它允许中断和放弃缓存存储操作。因此，它用于中止缓存响应，只要发生 IOException，当前缓存操作就会中止。因此，简单地说，它会中止缓存响应的尝试。

**语法:**

```
public abstract void abort()
```

**异常:**如果遇到任何输入输出错误，它会抛出 IOException

**方法二:**T2【getBody()方法

它只是返回一个输入流，可以从中访问响应体。

**语法:**

```
public abstract OutputStream getBody ()
```

**返回类型** : 输出应该启动响应的流。

**异常:**如果遇到任何输入输出错误，它会抛出 IOException

**实施:**

**示例**

## Java

```
// Java Program to illustrate CacheRequest Class
// java.net package

// Importing IOException class from
// java,io package
import java.io.IOException;
// Importing all classes from java.net package package
// to create an applet to run on anetwork
import java.net.*;
// Importing List and Map classes from
// java.util package
import java.util.List;
import java.util.Map;

// Main class
public class GFG {

    // Main driver method
    public static void main(String args[]) throws Exception
    {

        // Passing the string uri
        String ur = "https://www.geeksforgeeks.org";

        // Now, calling the constructor of the URI class
        URI ur1 = new URI(ur);

        // Passing the url
        URL url = new URL(
            "https://www.geeksforgeeks.org/category/java-programs/");

        // Now, calling the constructor of the URLConnection
        URLConnection uc = url.openConnection();

        ResponseCache responseCache = new ResponseCache() {
            // Calling the abstract methods
            public CacheResponse get(
                URI ur, String reqMethod,
                Map<String, List<String> > rqstHeaders)
                throws IOException
            {
                return null;
            }

            @Override
            public CacheRequest put(URI ur,
                                    URLConnection conn)
                throws IOException
            {
                return null;
            }
        };

        // Display message only
        System.out.println(
            "The put() method has been initiated and called Successfully!");

        // The put() method returns the
        // CacheRequest for recording
        System.out.println("The put() method returns: "
                           + responseCache.put(ur1, uc));
    }
}
```

**输出**

```
The put() method has been initiated and called Successfully!
The put() method returns: null
```

最后，我们结束了与这个类相关的纯粹的技术内容，让我们最终看一下这个类在现实世界中的应用。这个类间接用于软件人员的日常生活中，因为它提供了实现广泛通用性的网络应用程序的类。

*   network

*   Remote terminal access