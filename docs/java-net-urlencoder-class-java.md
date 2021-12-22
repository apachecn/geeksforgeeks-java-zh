# Java 中的 Java.net.URLEncoder 类

> 原文:[https://www . geesforgeks . org/Java-net-URL encoder-class-Java/](https://www.geeksforgeeks.org/java-net-urlencoder-class-java/)

这个类是一个用于 HTML 表单编码的实用程序类。编码使网址的形式更加可靠和安全。当 get 方法触发用户请求时，表单参数及其值会附加在 URL 末尾的“？”后面签名。当特殊字符用于它们的值时，问题就出现了。一般情况下，HTML 处理编码部分，自动处理特殊字符，并将其转换为特殊字符，以平滑处理所有操作。然而，仅仅依靠 HTML 特性并不是一个好的做法，因此 java 提供了这个类来显式编码 URL。
**对字符串进行编码时使用以下规则:**

1.  字母数字字符和某些特殊字符，如“ ***** ”、“ **_** ”、“**–**”和“**”。**'保持不变。
2.  空格转换成“ **+** ”符号。
3.  所有其他字符使用指定的编码方案由一个或多个字节编码。它们被转换成三个字符串形式 **%xy** ，其中 xy 代表编码字符的十六进制表示。W3C 推荐使用“UTF-8”进行编码。

例如，如果我们有包含特殊字符和空格的参数值

```java
u@geeks for geeks
```

如果使用的编码是最常用的 UTF-8，则@符号将转换为%40，空格将转换为+符号，我们的编码字符串看起来像-

```java
u%40geeks+for+geeks
```

**方法:**

1.  **encode() :** 这是这个类提供的唯一一个方法。顾名思义，它返回指定字符串的编码字符串。一种方法(现在已被否决)只有一个参数，即要编码的字符串。它不允许您指定要使用的编码，而是使用平台默认编码。另一个版本允许使用编码规范，因此被广泛使用。

    ```java
    Syntax :public static String encode(String s) - @Deprecated
    Parameters :
    s : String to be encoded

    ```

    ```java
    Syntax :public static String encode(String s,
                String enc)
                         throws UnsupportedEncodingException
    Parameters : 
    s : string to be encoded
    enc : encoding to be used
    Throws :
    UnsupportedEncodingException : If the specified encoding is not used

    ```

**Java 实现:**

```java
// Java program to show encode() method of 
// URLEncoder class
import java.io.UnsupportedEncodingException;
import java.net.MalformedURLException;
import java.net.URL;
import java.net.URLEncoder;

public class UrlEncoder 
{
    public static void main(String[] args) throws MalformedURLException, 
                                   UnsupportedEncodingException 
    {
        // base URL
        String baseurl = "https://www.geeksforgeeks.org/?q=";

        // String to be encoded
        String query = "u@geeks for geeks";

        System.out.println("URL without encoding :");
        URL url = new URL(baseurl + query);
        System.out.println(url);

        // encode() method
        System.out.println("URL after encoding :");
        url = new URL(baseurl + URLEncoder.encode(query, "UTF-8"));
        System.out.println(url);
    }

}
```

**输出:**

```java
URL without encoding :
https://www.geeksforgeeks.org/?q=u@geeks for geeks
URL after encoding :
https://www.geeksforgeeks.org/?q=u%40geeks+for+geeks
```

**参考文献:**
[Java 官方文档](https://docs.oracle.com/javase/7/docs/api/java/net/URLEncoder.html)
本文由 **Rishabh Mahrsee** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。