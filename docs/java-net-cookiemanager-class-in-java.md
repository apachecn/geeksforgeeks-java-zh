# java 中的 java.net.CookieManager 类

> 原文:[https://www . geesforgeks . org/Java-net-cookiemanager-class-in-Java/](https://www.geeksforgeeks.org/java-net-cookiemanager-class-in-java/)

[CookieManager 类](https://www.geeksforgeeks.org/java-net-httpcookie-java/)提供了 [CookieHandler](https://www.geeksforgeeks.org/java-net-httpcookie-java/) 的精确实现。这将 cookie 的存储与接受和拒绝 cookie 的策略分开。一个 CookieManager 用一个 CookieStore 和一个 CookiePolicy 初始化。CookieStore 管理存储，而 CookiePolicy 对象对 cookie 的接受/拒绝做出策略决定。

**语法:**

```java
public CookieManager()
// Create a new cookie manager
```

```java
public CookieManager(CookieStore store, CookiePolicy cookiePolicy)
// Create a new cookie manager 
// with specified cookie store and cookie policy
```

CookieManager 类中的方法如下表所示

<figure class="table">

| **Method** | Actions that have been performed |
| --- | --- |
| *getCookieStore（）* | This method will retrieve the current cookie store. |
| setcookiepolicy 策略(cookie 策略) | This method sets the cookie policy of this cookie manager. |
| get(URI uri，地图< String，List<string>>请求头)</string> | This method will get all applicable cookies of the URI specified in the request header from the cookie cache. |
| Put (URI uri, map > response header) | This method sets all applicable cookie. |

</figure>

让我们单独讨论这门课的所有四种方法，以便更好地理解。开始了。

**方法 1:**

getCookieStore()方法检索当前的 cookie 存储，并返回 cookie 管理器当前使用的 cookie 存储。

**语法:**

```java
public CookieStore getCookieStore() ;
```

**方法二:**

方法设置 cookie 管理器的 cookie 策略。默认情况下，CookieManager 的实例将具有 cookie 策略 ACCEPT _ ORIGINAL _ SERVER。可以调用此方法来设置另一个 cookie 策略。

**语法:**

```java
public void setCookiePolicy(CookiePolicy cookiePolicy) ;
```

**方法 3:**

get()方法从 cookie 缓存中获取请求头中所需 URI 的所有适用 cookie。实现需要考虑 URI，因此需要考虑 cookies 属性和安全设置，以确定应该返回哪一个。HTTP 的协议实现者应该确认，在添加了与选择 cookies 相关联的所有请求头之后，并且在发送请求之前，调用了该方法。

**语法:**

```java
public Map<String,List<String>> get(URI uri, Map<String,List<String>> requestHeaders)
```

**参数:**作为参数传递的 URI 指定了 cookies 的预期用途。特别是，该方案应该反映 cookies 是通过 HTTP、HTTPS 发送，还是在另一个上下文中使用，如 JavaScript。

**方法 4:**

put() 方法将所有适用的 Cookie 设置到 cookie 缓存中，例如，响应头中出现的名为 Set-Cookie2 的响应头字段。

**语法:**

```java
public void put(URI uri, Map<String,List<String>> responseHeaders)
```

**实施:**

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to illustrate getCookieStore()method of
// java.net.CookieManager Class

// java.net package is imported
// for network related things
import java.net.*;
// Importing List class from
// java.util pcckage
import java.util.List;

// Class
// To set CookiePolicy in JavaCookieManager Class
public class GFG {

    // Main driver method
    public static void main(String args[]) throws Exception
    {

        // Random URI as input
        String uri = "https://www.geeksforgeeks.org/";

        // Creating an object of Cookie Manager Class

        // Creating an object of CookieManager Class
        CookieManager cookieManager = new CookieManager();

        //  Setting and unsetting system wide Cookie Handler
        // using the setDefault() method
        CookieHandler.setDefault(cookieManager);

        // Pre-defined policy that accepts cookies
        // from original server.
        CookiePolicy cookiePolicy
            = CookiePolicy.ACCEPT_ORIGINAL_SERVER;

        // Setting the cookie policy of the cookieManager
        // class using the setCookiePolicy() method
        cookieManager.setCookiePolicy(cookiePolicy);

        // Now, creating an object of URL class
        URL url = new URL(uri);

        // Establishing the connection over the object
        // of URLConnection class
        URLConnection connection = url.openConnection();

        // Receiving the response
        connection.getContent();

        // Lastly, creating object of CookieStore to
        // retrieve current cookie store instance
        CookieStore cookieStore
            = cookieManager.getCookieStore();

        // For this, creating an List of object type
        // HttpCookie
        List<HttpCookie> cookieList
            = cookieStore.getCookies();

        // Iterating ove the List of objects
        // using the for each loop
        for (HttpCookie cookie : cookieList) {

            // Print the Domain name and Cookie name using
            // using getName() and getDomain() method
            System.out.println("Domain name is: "
                               + cookie.getDomain());
            System.out.println("Cookie name is: "
                               + cookie.getName());
        }
    }
}
```

**输出:**

```java
The Domain is: www.geeksforgeeks.org
java.net.InMemoryCookieStore@4590c9c3
```