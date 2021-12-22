# Java 中的 Java.net.URI 类

> 原文:[https://www.geeksforgeeks.org/java-net-uri-class-java/](https://www.geeksforgeeks.org/java-net-uri-class-java/)

这个类提供了从组件创建 URI 实例的方法，或者通过解析这些组件的字符串形式来访问和检索 URI 实例的不同组件的方法。
**什么是 URI？**
URI 代表统一资源标识符。统一资源标识符是用于标识特定资源的字符序列。它支持使用特定协议在网络上进行资源表示的交互。

**URI、URL 和 URN:有什么区别？**

你一定会想到这样一个问题:如果 URI 发现了一个资源，网址是做什么的？人们经常互换使用这些术语，但这是不正确的。根据蒂姆·伯纳斯·李

"统一资源标识符(URI)是一个紧凑的字符序列，用于标识抽象或物理资源."
“一个 URI 可以进一步分为定位器、名字或两者。术语“统一资源定位符”指的是 URI 子集，它通过表示资源的主要访问机制(例如，它们的网络“位置”)来标识资源，而不是通过名称或该资源的某些其他属性来标识资源。术语“统一资源名称”(URN)指的是即使资源不再存在或变得不可用，也需要保持全球唯一性和持久性的 URI 子集。”

例如，

```
https://www.geeksforgeeks.org/url-class-java-examples/
```

表示一个 url，因为它告诉在网络上可以找到 URL 类文章的确切位置。

```
url-class-java-examples
```

表示 URN，因为它不告诉任何关于位置的信息，而只给资源一个唯一的名称。

URI 类的对象和 URL 类的区别在于，URI 字符串仅在考虑语法的情况下被解析，而不在创建时执行主机查找。两个 URI 对象的比较仅在字符串中包含的字符上进行。但另一方面，一个网址字符串是用特定的方案解析的，两个网址对象的比较是通过查看网上的实际资源来完成的。

**URI 语法:**

```
scheme:[//[user:password@]host[:port]][/]path[?query][#fragment]
```

1.  **方案:**方案组件列出了与 URI 相关的协议。在一些方案中，需要“//”，而另一些方案则不需要。

    ```
    abc://admin:admin@geeksforgeeks.org:1234/path/data
                 ?key=value&key2=value2#fragid1
    ```

2.  **权限:**权限组件由几个组件组成-身份验证部分、主机和前面带“:”的可选端口号。认证部分包括用户名和密码。主机可以是任何 ip 地址。

    ```
    abc://admin:admin@geeksforgeeks.org:1234/path/data
                 ?key=value&key2=value2#fragid1
    ```

3.  **路径:**该路径代表一个字符串，该字符串包含服务器内到资源的地址。

    ```
    abc://admin:admin@geeksforgeeks.org:1234/path/data
                 ?key=value&key2=value2#fragid1
    ```

4.  **查询:**查询表示非层次数据，通常是用于搜索特定资源的查询。它们之间用“？”隔开从前面的部分。

    ```
    abc://admin:admin@geeksforgeeks.org:1234/path/data
                 ?key=value&key2=value2#fragid1
    ```

5.  **片段:**片段用于将二级资源标识为页面内的标题或副标题等。

    ```
    abc://admin:admin@geeksforgeeks.org:1234/path/data
                 ?key=value&key2=value2#fragid1
    ```

**施工人员:**

1.  **URI(字符串)**:通过解析指定的字符串构造一个 URI 对象。解析时使用的语法是 RFC 2396 附录 a

    ```
    Syntax :public URI(String str)
        throws URISyntaxException
    Parameters : 
    str : String to be parsed into URI
    Throws : 
    URISyntaxException : If the string violates RFC 2396
    ```

    中规定的语法
2.  **URI(String scheme, String ssp, String fragment)** : Constructs a URI from the given components. A component may be left undefined by passing null. Initially the result string is empty. If scheme is not null it is appended. Similarly the ssp and fragment part is appended if provided.

    ```
    Syntax :public URI(String scheme, String ssp, String fragment)
        throws URISyntaxException
    Parameters : 
    scheme : scheme name
    ssp : scheme-specific part
    fragment : fragment part
    Throws : 
    URISyntaxException : If the URI string constructed from the given
     components violates RFC 2396
    ```

    类似地，根据创建时已知的组件提供其他构造函数。

3.  **URI(字符串方案，字符串用户信息，字符串主机，内部端口，字符串路径，
    字符串查询，字符串片段)**

```
Syntax :public URI(String scheme, String userInfo, String host, int port, 
      String path, String query, String fragment)
Parameters :
scheme : string representing scheme
userInfo : userinfo of URI
host : host component of URI
port : listening port number
path : path of URI
query : String representing the query part
fragment :optional fragment 

```

*   **URI(字符串方案、字符串主机、字符串路径、字符串片段)**

    ```
    Syntax :public URI(String scheme, String host, String path, String fragment)
    Parameters :
    scheme : string representing scheme
    host : host component of URI
    path : path of URI
    fragment :optional fragment 

    ```

    *   **URI(String scheme, String authority, String path, String query, String fragment)**

    ```
    Syntax :public URI(String scheme, String authority, String path,
     String query, String fragment)
    Parameters :
    scheme : string representing scheme
    authority : authority
    path : path of URI
    query : String representing the query part

    ```

    **方法:**

    1.  **创建():**创建一个新的 URI 对象。这个方法可以称为伪构造函数。它是在已知给定的字符串将被解析为 URI 对象的情况下使用的，如果不解析，它将被认为是程序员的错误。

        ```
        Syntax : public static URI create(String str)
        Parameters :
        str : String to be parsed as URI
        ```

    2.  **parseServerAuthority() :** 如果提供了用户信息、主机和端口组件，该方法用于解析 URI 的权限组件。此方法返回一个 URI 对象，该对象的权限字段已被解析为基于服务器的权限。

        ```
        Syntax : public URI parseServerAuthority()
        ```

    3.  **normalize() :** 使这个 URI 的路径正常化。URI 是通过使 URI 路径正常化来构建的，这与 RFC 2396 是一致的。返回一个规范化的 URI 对象。

        ```
        Syntax : public URI normalize()
        ```

    4.  **resolve() :** Resolves the given URI with this URI. Returns a new hierarchical URI in a manner consistent with RFC 2396.

        ```
        Syntax : public URI resolve(URI uri)
        Parameters :
        uri : URI to be resolved

        ```

        另一个重载方法，以字符串作为参数，相当于调用 resolve(URI.create(str))。

        ```
        Syntax : public URI resolve(String str)
        Parameters :
        str : String to be parsed as URI
        ```

    5.  **relativize() :** Relativizes the given URI against this URI.

        ```
        Syntax : public URI relativize(URI uri)
        ```

        **参数:**
        uri : URI 相对化

    6.  **Tour():**从这个 URI 构建一个网址。

        ```
        Syntax : public URL toURL()
                  throws MalformedURLException
        Throws :
        MalformedURLException : If error occurs while constructing URL
        ```

    7.  **getScheme() :** 返回 URI 的方案组件

        ```
        Syntax : public String getScheme()
        ```

    8.  **GetRawSchemespecificpart():**返回 URI 的原始方案特定组件。

        ```
        Syntax : public String getRawSchemeSpecificPart()
        ```

    9.  **getSchemeSpecificPart() :** 返回 URI 的解码方案特定组件

        ```
        Syntax : public String getSchemeSpecificPart()
        ```

    10.  **getRawAuthority() :** 返回 URI 的权威组件。如果权限是基于服务器的，则返回进一步的用户信息、主机和端口组件。

        ```
        Syntax : public String getRawAuthority()
        ```

    11.  **getAuthority() :** 返回与上述方法完全相似的结果，除了解码形式。

        ```
        Syntax : public String getAuthority()
        ```

    12.  **getRawUserInfo() :** 返回 URI 的用户信息组件，如果未定义则返回 null。

        ```
        Syntax : public String getRawUserInfo()
        ```

    13.  **getUserInfo() :** Returns the user info component of the URI in decoded form, or null if it is undefined.

        ```
        Syntax : public String getUserInfo()
        ```

        **Java 实现:**

        ```
        // Java program to illustrate various
        // URI class methods
        import java.net.*;

        class uridemo1
        {
            public static void main(String[] args) throws Exception 
            {
                String uribase = "https://www.geeksforgeeks.org/";
                String urirelative = "languages/../java";
                String str = "https://www.google.co.in/?gws_rd=ssl#"+""
                        + "q=networking+in+java+geeksforgeeks"+""
                        +"&spf=1496918039682";

                // Constructor to create a new URI
                // by parsing the string
                URI uriBase = new URI(uribase);

                // create() method
                URI uri = URI.create(str);

                // toString() method
                System.out.println("Base URI = " + uriBase.toString());

                URI uriRelative = new URI(urirelative);
                System.out.println("Relative URI = " + uriRelative.toString());

                // resolve() method
                URI uriResolved = uriBase.resolve(uriRelative);
                System.out.println("Resolved URI = " + uriResolved.toString());

                // relativized() method
                URI uriRelativized = uriBase.relativize(uriResolved);
                System.out.println("Relativized URI = " + uriRelativized.toString());

                // normalize() method
                System.out.println(uri.normalize().toString());

                // getScheme() method
                System.out.println("Scheme = " + uri.getScheme());

                // getRawShemeSpecific() method
                System.out.println("Raw Scheme = " + uri.getRawSchemeSpecificPart());

                // getSchemeSpecificPart() method
                System.out.println("Scheme-specific part = " + uri.getSchemeSpecificPart());

                // getRawUserInfo() method
                System.out.println("Raw User Info = " + uri.getRawUserInfo());

                // getUserInfo() method
                System.out.println("User Info = " + uri.getUserInfo());

                // getAuthority() method
                System.out.println("Authority = " + uri.getAuthority());

                // getRawAuthority() method
                System.out.println("Raw Authority = " + uri.getRawAuthority());

            }
        }
        ```

        **输出:**

        ```
        Base URI = https://www.geeksforgeeks.org/
        Relative URI = languages/../java
        Resolved URI = https://www.geeksforgeeks.org/java
        Relativized URI = java
        https://www.google.co.in/?gws_rd=ssl#q=networking+in+
        java+geeksforgeeks&spf=1496918039682
        Scheme = https
        Raw Scheme = //www.google.co.in/?gws_rd=ssl
        Scheme-specific part = //www.google.co.in/?gws_rd=ssl
        Raw User Info = null
        User Info = null
        Authority = www.google.co.in
        Raw Authority = www.google.co.in

        ```

    14.  **getHost() :** 返回 URI 的主机组件。由于 URI 的主机组件不能包含转义八位字节，因此该方法不执行任何解码。

        ```
        Syntax : public String getHost()
        ```

    15.  **getPort() :** 返回该 URI 的端口号。

        ```
        Syntax : public int getPort()
        ```

    16.  **getRawPath() :** 返回此 URI 的原始路径，如果未定义，则返回 null。

        ```
        Syntax : public String getRawPath()
        ```

    17.  **getPath() :** 返回这个 URI 的解码路径部分。

        ```
        Syntax : public String getPath()
        ```

    18.  **getRawQuery() :** 返回 URI 的查询组件，如果未定义则返回 null。

        ```
        Syntax : public String getRawQuery()
        ```

    19.  **getQuery() :** 以解码形式返回 URI 的查询组件，如果未定义则返回 null。

        ```
        Syntax : public String getQuery()
        ```

    20.  **getrawlfragment():**返回 URI 的片段组件，如果未定义则返回 null。

        ```
        Syntax : public String getRawFragment()
        ```

    21.  **getFragment() :** 返回该 URI 的解码片段组件，如果未定义则返回 null。

        ```
        Syntax : public String getFragment()
        ```

    22.  **compareTo() :** 将这个 URI 对象与另一个 URI 对象进行比较。使用 String.compareTo()方法根据自然顺序执行比较。如果一个组件未定义，而另一个组件的定义小于第一个，则认为该组件小于第二个组件。要解析的组件以原始形式而不是编码形式进行比较。

        ```
        Syntax : public int compareTo(URI uri)
        Parameters :
        uri : URI to be compared with
        ```

    23.  **等于():**用这个 URI 测试给定的对象。Ig 对象不是 URI，它返回 false。要让两个 URIs 被认为是平等的，就要求两者要么都不透明，要么都是等级制的。当检查不同组件的相等性时，会考虑它们的原始形式，而不是编码形式。

        ```
        Syntax : public boolean equals(Object ob)
        Parameters :
        ob : object to be compared for equality
        ```

    24.  **isabsolut():**如果这个 URI 是绝对的，则返回真，否则返回假。一个 URI 是绝对的，当且仅当，它有一个计划的组成部分。

        ```
        Syntax : public boolean isAbsolute()
        ```

    25.  **isOpaque() :** 如果该 URI 不透明，则返回 true，否则返回 false。当且仅当 URI 是绝对的，并且其方案特定部分不以斜杠字符('/')

        ```
        Syntax : public boolean isOpaque()
        ```

        开头时，它是不透明的
    26.  **hashCode() :** 返回这个 URI 对象的 hashCode。为 URI 对象创建 hashcode 时，会考虑所有组件。

        ```
        Syntax : public int hashCode()
        ```

    27.  **toString() :** 返回这个 URI 对象的字符串表示形式。

        ```
        Syntax : public String toString()
        ```

    28.  **toASCIIString() :** Returns the string representation in ASCII format.

        ```
        Syntax : public String toASCIIString()
        ```

        **Java 实现**:

        ```
        //Java Program to illustrate various
        //URI class methods
        import java.net.*;
        class uridemo1 
        {
            public static void main(String[] args) throws Exception 
            {
                String str = "https://www.google.co.in/?gws_rd=ssl#"+""
                        + "q=networking+in+java+geeksforgeeks"+""
                        +"&spf=1496918039682";

                // Constructor to create a new URI
                // by parsing the given string.
                URI uri = new URI(str);

                // getHost() method
                System.out.println("Host = " + uri.getHost());

                // getPort() method
                System.out.println("Port = " + uri.getPath());

                // getRawPath() method
                System.out.println("Raw Path = " + uri.getRawPath());

                // getPath() method
                System.out.println("Path = " + uri.getPath());

                // getQuery() method
                System.out.println("Query = " + uri.getQuery());

                // getRawQuery() method
                System.out.println("Raw Query = " + uri.getRawQuery());

                // getFragment() method
                System.out.println("Fragment = " + uri.getFragment());

                // getRawFragment() method
                System.out.println("Raw Fragment = " + uri.getRawFragment());

                URI uri2 = new URI(str + "fr");

                // compareTo() mrthod
                System.out.println("CompareTo =" + uri.compareTo(uri2));

                // equals() method
                System.out.println("Equals = " + uri.equals(uri2));

                // hashcode() method
                System.out.println("Hashcode : " + uri.hashCode());

                // toString() method
                System.out.println("toString : " + uri.toString());

                // toASCIIString() method
                System.out.println("toASCIIString : " + uri.toASCIIString());

            }
        }
        ```

        **输出:**

        ```
        Host = www.google.co.in
        Port = /
        Raw Path = /
        Path = /
        Query = gws_rd=ssl
        Raw Query = gws_rd=ssl
        Fragment = q=networking+in+java+geeksforgeeks&spf=1496918039682
        Raw Fragment = q=networking+in+java+geeksforgeeks&spf=1496918039682
        CompareTo =-2
        Equals = false
        Hashcode : 480379574
        toString : https://www.google.co.in/?gws_rd=ssl#q=networking+
        in+java+geeksforgeeks&spf=1496918039682
        toASCIIString : https://www.google.co.in/?gws_rd=ssl#q=
        networking+in+java+geeksforgeeks&spf=1496918039682

        ```

**参考资料:**
[官方 Java 文档](https://docs.oracle.com/javase/7/docs/api/java/net/URI.html)

本文由**里沙布·马赫塞**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。