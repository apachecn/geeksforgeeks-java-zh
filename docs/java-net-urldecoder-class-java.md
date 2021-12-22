# Java 中的 Java . net . urldector 类

> 原文:[https://www . geesforgeks . org/Java-net-URL decoder-class-Java/](https://www.geeksforgeeks.org/java-net-urldecoder-class-java/)

这是一个用于 HTML 表单解码的实用程序类。它只是执行与 URLEncoder 类相反的操作，即给定一个编码字符串，它使用指定的方案对其进行解码。通常在 servlet 编程中使用 getParameter()方法访问请求的内容时，值会在返回之前自动解码。但有时可能需要显式解码否则会被 URL 编码的字符串。
**对字符串进行解码时遵循以下步骤:**

1.  字母数字字符和某些特殊字符，如“ ***** ”、“ **_** ”、“**–**”和“**”。**'保持不变。
2.  **+** '符号转换为空格。
3.  所有其他字符都使用指定的编码方案进行解码。形式为 **%xy** 的字符串被转换为其编码会导致这种三字符表示的字符。W3C 推荐使用“UTF-8”进行编码。

例如，编码的字符串

```java
u%40geeks+for+geeks
```

将被转换为字符串表示形式，其中%40 将被@符号替换，而+符号将被转换为空格字符。

```java
u@geeks for geeks
```

**方法:**

**decode() :**

```java
Syntax :public static String decode(String s)- @Deprecated
Parameters :
s : encoded string to be decoded

```

```java
Syntax :public static String decode(String s,
            String enc)
                     throws UnsupportedEncodingException
Parameters : 
s : string to be decoded
enc : encoding to be used
Throws :
UnsupportedEncodingException : If the specified encoding is not used

```

**Java 实现:**

```java
// Java program to show decode() method of 
// URLDecoder class
import java.io.UnsupportedEncodingException;
import java.net.URLDecoder;

public class urlDecoder 
{
    public static void main(String[] args) 
                             throws UnsupportedEncodingException 
    {
        // encoded string
        String encodedString = "u%40geeks+for+geeks";
        System.out.println("Encoded String :");
        System.out.println(encodedString);

        // decode() method
        System.out.println("Decoded String :");
        System.out.println(URLDecoder.decode(encodedString, "UTF-8"));
    }
}
```

**输出:**

```java
Encoded String :
u%40geeks+for+geeks
Decoded String :
u@geeks for geeks

```

**参考文献:**
[Java 官方文档](https://docs.oracle.com/javase/7/docs/api/java/net/URLDecoder.html)
本文由 **Rishabh Mahrsee** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。