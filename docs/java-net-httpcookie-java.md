# Java 中的 Java . net . httpookie

> 哎哎哎:# t0]https://www . geeksforgeeks . org/Java-net-http cookie-Java/

先决条件–[饼干](https://www.geeksforgeeks.org/cookies-used-website/)

许多网站使用称为 cookies 的小字符串来存储连接之间的持久客户端状态。Cookies 在请求和响应的 HTTP 头中从服务器传递到客户端，然后再传递回来。服务器可以使用 Cookies 来指示会话标识、购物车内容、登录凭据、用户首选项等。

一个 HttpCookie 对象代表一个 http cookie，它携带服务器和用户代理之间的状态信息。Cookie 被广泛用于创建有状态会话。
有 3 个 http cookie 规范:

*   网景草稿
*   RFC 2109
*   RFC 2965

HttpCookie 类可以接受所有这 3 种形式的语法。

**构造函数:**用指定的名称和值创建一个 cookie。该名称必须仅包含 ASCII 字母数字字符，并符合 RFC 2965。如果名称不正确，它将引发 IllegalArgument 异常；如果名称为空，它将引发 NullPointerException 异常。该值可以是 cookie 想要存储的任何内容。

```java
Syntax : public HttpCookie(String name,
          String value)
Parameters :
name : name of cookie
value : value of cookie
Throws :
IllegalArgumentException : if name does not conform to RFC2965
NullPointerException : if name is null
```

**方法:**

1.  **parse() :** 返回从头字符串解析的 cookies 列表。标头必须以 set-cookie 或 set-cookie2 标记开头，或者根本不能包含任何标记。

    ```java
    Syntax : public static List parse(String header)
    Parameters : 
    header : String to be parsed as cookies
    ```

2.  **hasExpired() :** 返回布尔值，指示 cookie 是否已过期。

    ```java
    Syntax : public boolean hasExpired()
    ```

3.  **setComment() :** 用于设置描述 cookie 用途的简短描述。它用于何时向用户呈现 cookie。

    ```java
    Syntax : public void setComment(String purpose)
    Parameters :
    purpose : purpose of cookie
    ```

4.  **getComment() :** 返回 cookie 的描述，如果 cookie 没有注释，则返回 null。

    ```java
    Syntax : public void getComment()
    ```

5.  **setCommentURL() :** 用于设置描述 cookie 用途的简短评论 URL。当浏览器将 cookie 呈现给用户时使用。

    ```java
    Syntax : public void setCommentURL(String purpose)
    Parameters :
    purpose : purpose of cookie
    ```

6.  **getCommentURL() :** 返回 cookie 的 URL 注释，如果 cookie 没有 URL 注释，则返回 null。

    ```java
    Syntax : public String getComment()
    ```

7.  **设置丢弃():**用于设置用户代理是否应该丢弃该 cookie。

    ```java
    Syntax : public void setDiscard(Boolean discard)
    Parameters :
    discard : true if UA should discard, otherwise false
    ```

8.  **getDiscard() :** 返回 setDiscard()方法设置的丢弃变量的状态。更具体地说，如果 UA 要丢弃此 cookie，则返回 true，否则返回 false。

    ```java
    Syntax : public Boolean getDiscard()
    ```

9.  **设定端口列表():**用于指定该 cookie 可以使用的端口。

    ```java
    Syntax : public void setPortList(String portList)
    Parameters :
    portList : String of comma separated digits specifying the ports.
    ```

10.  **getPortList() :** 返回该 cookie 可以使用的端口列表。

    ```java
    Syntax : public String getPortList()
    ```

11.  **设置域():**指定该 cookie 应该可见的域。例如，从 bali.vacations.com 的 servlet 发送的 cookies 通常不会被浏览器返回到 queensland.vacations.com 的页面。如果站点希望发生这种情况，servlets 可以指定 cookie.setDomain(“.休假. com”)。为了防止服务器设置适用于域外主机的 cookies，指定的域必须满足以下要求:它必须以点开始(例如. coreservlets.com)。

    ```java
    Syntax : public void setDomain(String domain)
    Parameters :
    domain : String representing the domain in which this cookie is visible
    ```

12.  **getDomain() :** 返回该 cookie 可见的域。

    ```java
    Syntax : public String getDomain()
    ```

13.  **设置最大年龄():**用于设置饼干的最大年龄(秒)。它指定在创建 cookie 后它存在的最长时间。负值表示浏览器一退出，cookie 就会过期。

    ```java
    Syntax : public void setMaxAge(long age)
    Parameters :
    age : Max survive time in seconds
    ```

14.  **getMaxAge() :** 返回 cookie 的最大年龄。

    ```java
    Syntax : public long getMaxAge()
    ```

15.  **setPath() :** 用于指定客户端返回 cookie 的路径。此 cookie 对指定路径的所有页面和子目录都可见。例如，如果服务器从 http://ecommerce.site.com/toys/specials.html,发送了 cookie，浏览器将在连接到 http://ecommerce.site.com/to/beginners.html,而不是 http://ecommerce.site.com/c/classic.html.时发回 cookie

    ```java
    Syntax : public void setPath(String uri)
    Parameters :
    uri - a String specifying a path
    ```

16.  **getPath() :** Returns the path set for this cookie.

    ```java
    Syntax : public String getPath()
    ```

    **Java 实现:**

    ```java
    // Java Program to illustrate various
    // methods of java.net.HttpCookie class
    public class httpcookie1 
    {

        public static void main(String[] args) 
        {

            // Constructor to create a new cookie.
            HttpCookie cookie = new HttpCookie("First", "1");

            // setComment() method
            cookie.setComment("Just for explanation");

            // getComment() method
            System.out.println("Comment : " + cookie.getComment());

            // setCommentURL() method
            cookie.setCommentURL("192.168.1.1");

            // getCommentURL() method
            System.out.println("CommentURL : " + cookie.getCommentURL());

            // setDiscard() method
            cookie.setDiscard(true);

            // getDiscard() method
            System.out.println("Discard : " + cookie.getDiscard());

            // setPortlist() method
            cookie.setPortlist("1001,8520");

            // getPortList() method
            System.out.println("Ports: " + cookie.getPortlist());

            // setDomain() method
            cookie.setDomain(".localhost.com");

            // getDomain() method
            System.out.println("Domain : " + cookie.getDomain());

            // setMaxAge() method
            cookie.setMaxAge(3600);

            // getMaxAge() method
            System.out.println("Max Age : " + cookie.getMaxAge());

            // setPath() method
            cookie.setPath("192.168.1.1/admin/index.html");

            // getPath() method
            System.out.println("Path: " + cookie.getPath());

        }

    }
    ```

    **输出**

    ```java
    Comment : Just for explanation
    CommentURL : 192.168.1.1
    Discard : true
    Ports: 1001,8520
    Domain : .localhost.com
    Max Age : 3600
    Path: 192.168.1.1/admin/index.html
    ```

17.  **设置安全():**指示发送此 cookie 时是否使用安全协议。默认值为假。

    ```java
    Syntax : public void setSecure(boolean secure)
    Parameters:
    secure - If true, the cookie can only be sent over a secure protocol like https. 
    If false, it can be sent over any protocol.
    ```

18.  **getSecure() :** 如果该 cookie 必须通过安全协议发送，则返回 true，否则返回 false。

    ```java
    Syntax : public boolean getSecure()
    ```

19.  **getName() :** 返回 cookie 的名称。

    ```java
     Syntax : public String getName()
    ```

20.  **设置值():**初始化后为 cookie 分配新值。

    ```java
    Syntax : public void setValue(String newValue)
    Parameters :
    newValue - a String specifying the new value
    ```

21.  **getValue :** 返回 cookie 的值。

    ```java
    Syntax : public String getValue()
    ```

22.  **getVersion() :** 如果 cookie 符合原网景规范，则返回 0；1 如果饼干符合 RFC 2965/2109

    ```java
    Syntax : public int getVersion()
    ```

23.  **setVersion() :** 用于设置该 cookie 使用的 cookie 协议版本。

    ```java
    Syntax :public void setVersion(int v)
                   throws IllegalArgumentException
    Parameters :
    v - 0 for original Netscape specification; 1 for RFC 2965/2109
    Throws :
    IllegalArgumentException - if v is neither 0 nor 1
    ```

24.  **isHttpOnly() :** 如果 cookie 只能被 http 使用，即不能被 JS、vb 等脚本语言使用，则返回 true。

    ```java
    Syntax : public boolean isHttpOnly()
    ```

25.  **setHttpOnly() :** 用于设置该 cookie 是否仅用于 http。

    ```java
    Syntax : public void setHttpOnly(boolean httpOnly)
    Parameters :
    httpOnly - if true make the cookie HTTP only, i.e. only visible as part 
    of an HTTP request.
    ```

26.  **域名匹配():**检查主机名是否在域中的实用程序功能。

    ```java
    Syntax : public static boolean domainMatches(String domain,
                        String host)
    Parameters :
    domain : domain to check hostname with
    host : host to check
    ```

27.  **toString() :** 构造此 cookie 的字符串表示形式。

    ```java
     Syntax :public String toString()
    ```

28.  **equals() :** 如果两个 http cookies 彼此相等，则返回 true，否则返回 false。

    ```java
     Syntax :public boolean equals(Object obj)
    ```

29.  **hashCode() :** 返回这个 http cookie 的哈希代码。结果是这个 cookie 的三个重要组成部分:名称、域和路径的哈希代码值的总和。覆盖类对象中的哈希代码。

    ```java
    Syntax : public int hashCode()
    ```

30.  **克隆():**创建并返回此对象的副本。重写对象类的克隆方法。

    ```java
    Syntax : public Object clone()
    ```

**Java 实现:**

```java
// Java Program to illustrate various
// methods of java.net.HttpCookie class
import java.net.HttpCookie;

public class httpcookie1 
{

    public static void main(String[] args) 
    {

        // Constructor to create a new cookie.
        HttpCookie cookie = new HttpCookie("First", "1");

        // setSecure() method
        cookie.setSecure(true);

        // getSecure() method
        System.out.println("Secure : " + cookie.getSecure());

        // getName() method
        System.out.println("Name : " + cookie.getName());

        // setValue() method : can be used to modify value of cookie.
        cookie.setValue("2");

        // getvalue() method
        System.out.println("Value : " + cookie.getValue());

        // setVersion() method
        cookie.setVersion(1);

        // getVersion() method
        System.out.println("Version : " + cookie.getVersion());

        // setHttPonly() method
        cookie.setHttpOnly(true);

        // isHttpOnly() method
        System.out.println("is HTTP only : " + cookie.isHttpOnly());

        // toString() method
        System.out.println("toString : " + cookie.toString());

        // hashcode() method
        System.out.println("Hashcode : " + cookie.hashCode());

    }

}
```

**输出:**

```java
Secure : true
Name : First
Value : 2
Version : 1
is HTTP only : true
toString : First="2"
Hashcode : 97440432
```

另一个例子展示了 cookie 实际上是如何被网络服务器使用的，其中我们打印了 www.facebook.com 存储的 cookie 的详细信息

```java
import java.io.IOException;
import java.net.CookieHandler;
import java.net.CookieManager;
import java.net.CookieStore;
import java.net.HttpCookie;
import java.net.URL;
import java.net.URLConnection;
import java.util.List;

public class httpcookie1 
{

    public static void main(String[] args) throws IOException 
    {

        String urlString = "https://www.facebook.com";

        // Create a default system-wide CookieManager
        CookieManager cookieManager = new CookieManager();

        CookieHandler.setDefault(cookieManager);

        // Open a connection for the given URL
        URL url = new URL(urlString);
        URLConnection urlConnection = url.openConnection();
        urlConnection.getContent();

        // Get CookieStore which is the default internal in-memory
        CookieStore cookieStore = cookieManager.getCookieStore();

        // Retrieve all stored HttpCookies from CookieStore
        List<HttpCookie> cookies = cookieStore.getCookies();

        int cookieIdx = 0;

        // Iterate HttpCookie object
        for (HttpCookie ck : cookies) {

            System.out.println("------ Cookie." + ++cookieIdx + " -------");

            // Get the cookie name
            System.out.println("Cookie name: " + ck.getName());

            // Get the domain set for the cookie
            System.out.println("Domain: " + ck.getDomain());

            // Get the max age of the cookie
            System.out.println("Max age: " + ck.getMaxAge());

            // Get the path of the server
            System.out.println("Server path: " + ck.getPath());

            // Get boolean if the cookie is being restricted to a secure
            // protocol
            System.out.println("Is secured: " + ck.getSecure());

            // Gets the value of the cookie
            System.out.println("Cookie value: " + ck.getValue());

            // Gets the version of the protocol with which the given cookie is
            // related.
            System.out.println("Cookie protocol version: " + ck.getVersion());

        }
    }

}
```

**输出:**

```java
------------------ Cookie.1 ------------------
Cookie name: fr
Domain: .facebook.com
Max age: 7775999
Server path: /
Is secured: true
Cookie value: 0Xj7tBSsWlmtXPo92..BZFC8G.qC.AAA.0.0.BZFC8G.AWUwiIgM
Cookie protocol version: 0
```

**参考:**
[官方 Java 文档](https://docs.oracle.com/javase/7/docs/api/java/net/HttpCookie.html)

本文由**里沙布·马赫塞**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。