# java 中的 java.net.CookieHandler 类

> 原文:[https://www . geesforgeks . org/Java-net-cookiehandler-class-in-Java/](https://www.geeksforgeeks.org/java-net-cookiehandler-class-in-java/)

Java 中 **CookieHandler 类**的对象提供了一种回调机制，用于将 HTTP 状态管理策略实现挂接到 HTTP 协议处理程序中。如何发出 HTTP 请求和响应的机制由 HTTP 状态管理机制指定。

HTTP 协议处理程序也使用的系统范围的 CookieHandler 通常通过执行 CookieHandler . setdefault(CookieHandler)来注册。当前注册的 CookieHandler 通常通过调用 CookieHandler.getDefault()来检索。

**申报:**

```
public abstract class CookieHandler
extends Object
```

**施工方:**

```
CookieHandler();
```

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate the usage
// of CookieHandler Class

import java.net.CookieHandler;
import java.net.CookieManager;
import java.net.CookieStore;
import java.net.HttpCookie;
import java.net.URL;
import java.net.URLConnection;
import java.util.List;
public class JavaCookieHandlerExample1 {
    public static void main(String args[]) throws Exception
    {

        String uri = "https://www.google.com";

        // Instantiate CookieManager;
        CookieManager c = new CookieManager();

        // First set the default cookie manager.
        CookieHandler.setDefault(c);
        URL url = new URL(uri);

        // All the following subsequent URLConnections
        // will use the same cookie manager.
        URLConnection connection = url.openConnection();
        connection.getContent();

        // Get cookies from underlying CookieStore
        CookieStore cookieStore = c.getCookieStore();

        List<HttpCookie> cookieList
            = cookieStore.getCookies();

        for (HttpCookie cookie : cookieList) {

            // Get domain set for the cookie
            System.out.println("The domain is: "
                               + cookie.getDomain());
        }
    }
}
```

**输出:**

```
The domain is: .google.com
```

**CookieHandler 类在 Java 中提供了** **以下方法:**

<figure class="table">

| **Method** | **Description** |
| --- | --- |
| get（URI uri，地图 < String，List <string>>requestHeaders）</string> | This method gets all applicable cookies of the URI specified in the request from the cookie cache. |
| getDefault（） | This method gets the system-wide cookie handler. |
| put(URI uri，映射< String，List<string>>响应头)</string> | This method sets all applicable Cookies, for example, the response header field named Set-Cookie2, which is presented to cookie cache in the response header. |
| 设置默认值(CookieHandler 钱德勒) | This method sets or unsets the system-wide cookie handler. |

</figure>