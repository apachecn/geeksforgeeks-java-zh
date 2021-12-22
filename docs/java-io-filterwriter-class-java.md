# Java 中的 Java.io.FilterWriter 类

> 原文:[https://www . geesforgeks . org/Java-io-filter writer-class-Java/](https://www.geeksforgeeks.org/java-io-filterwriter-class-java/)

用于编写过滤字符流的抽象类。抽象类 FilterWriter 本身提供默认方法，将所有请求传递给包含的流。FilterWriter 的子类应该覆盖这些方法中的一些，并且还可以提供额外的方法和字段。
**建造师:**

*   **受保护**过滤编写器(编写器退出):**** 创建新的过滤编写器。

**方法:**

*   **虚空关闭():**关闭溪流，先冲洗。一旦流被关闭，进一步的 write()或 flush()调用将导致引发 IOException。关闭以前关闭的流没有效果。

    ```java
    Syntax :public void close()
               throws IOException
    Throws:
    IOException 
    ```

*   **虚空冲():**冲溪。

    ```java
    Syntax :public void flush()
               throws IOException
    Throws:
    IOException
    ```

*   **void write(char[] cbuf，int off，int len) :** 写入字符数组的一部分。

    ```java
    Syntax :public void write(char[] cbuf,
             int off,
             int len)
               throws IOException
    Parameters:
    cbuf - Buffer of characters to be written
    off - Offset from which to start reading characters
    len - Number of characters to be written
    Throws:
    IOException
    ```

*   **void write(int c) :** 写单个字符。

    ```java
    Syntax :public void write(int c)
               throws IOException
    Parameters:
    c - int specifying a character to be written
    Throws:
    IOException
    ```

*   **空写(字符串，int off，int len) :** 写字符串的一部分。

    ```java
    Syntax :public void write(String str,
             int off,
             int len)
               throws IOException
    Parameters:
    str - String to be written
    off - Offset from which to start reading characters
    len - Number of characters to be written
    Throws:
    IOException 
    ```

**程序:**

```java
//Java program demonstrating FilterWriter methods
import java.io.FilterWriter;
import java.io.StringWriter;
import java.io.Writer;
class FilterWriterDemo
{
    public static void main(String[] args) throws Exception
    {
        FilterWriter fr = null;
        Writer wr = null;
        wr = new StringWriter();
        fr = new FilterWriter(wr) {} ;
        String str = "Geeksfor";
        char c[] = {'G','e','e','k'};

        //illustrating write(String str,int off,int len)
        fr.write(str);

        //illustrating flush()
        fr.flush();

        //illustrating write(char[] cff,int off,int len)
        fr.write(c);

        //illustrating write(int c)
        fr.write('s');
        System.out.print(wr.toString());

        //close the stream
        fr.close();
    }
}
```

**输出:**

```java
GeeksforGeeks
```

本文由 **[尼尚·夏尔马](https://www.facebook.com/ChippingEye2766)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。