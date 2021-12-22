# Java 中的 Java.io.Reader 类

> 原文:[https://www.geeksforgeeks.org/java-io-reader-class-java/](https://www.geeksforgeeks.org/java-io-reader-class-java/)

这是一个用于读取字符流的抽象类。子类必须实现的唯一方法是 read(char[]、int、int)和 close()。然而，大多数子类将覆盖这里定义的一些方法，以便提供更高的效率、额外的功能或两者兼而有之。
**施工人员:**

*   **受保护的读取器():**创建一个新的字符流读取器，其关键部分将在读取器本身上同步。
*   **受保护的读取器(对象锁):**创建一个新的字符流读取器，其关键部分将在给定的对象上同步。

**方法:**

*   **抽象 void close() :** 关闭流并释放与之关联的任何系统资源。一旦流被关闭，进一步的 read()、ready()、mark()、reset()或 skip()调用将引发 IOException。关闭以前关闭的流没有效果。

    ```java
    Syntax :public abstract void close()
                        throws IOException
    Throws:
    IOException 
    ```

*   **空标记(int readAheadLimit) :** 标记溪流中的当前位置。对 reset()的后续调用将尝试将流重新定位到这一点。并非所有字符输入流都支持 mark()操作。

    ```java
    Syntax :public void mark(int readAheadLimit)
              throws IOException
    Parameters:
    readAheadLimit - Limit on the number of characters that may be read
    while still preserving the mark. After reading this many characters, 
    attempting to reset the stream may fail.
    Throws:
    IOException 
    ```

*   **布尔型 markSupported() :** 告知此流是否支持 mark()操作。默认实现总是返回 false。子类应该重写此方法。

    ```java
    Syntax :public boolean markSupported()
    Returns:
    true if and only if this stream supports the mark operation.
    ```

*   **int read() :** 读取单个字符。此方法将一直阻塞，直到某个字符可用、出现输入/输出错误或到达流的末尾。
    想要支持高效单字符输入的子类应该覆盖这个方法。

    ```java
    Syntax :public int read()
             throws IOException
    Returns:
    The character read, as an integer in the range 0 to 65535 (0x00-0xffff), 
    or -1 if the end of the stream has been reached
    Throws:
    IOException 
    ```

*   **int read(char[] cbuf) :** 将字符读入数组。此方法将一直阻塞，直到有一些输入可用、出现输入/输出错误或到达流的末尾。

    ```java
    Syntax :public int read(char[] cbuf)
             throws IOException
    Parameters:
    cbuf - Destination buffer
    Returns:
    The number of characters read, or -1 if the end of the stream has been reached
    Throws:
    IOException 
    ```

*   **抽象 int read(char[] cbuf，int off，int len) :** 将字符读入数组的一部分。此方法将一直阻塞，直到有一些输入可用、出现输入/输出错误或到达流的末尾。

    ```java
    Syntax :public abstract int read(char[] cbuf,
           int off,
           int len)
                      throws IOException
    Parameters:
    cbuf - Destination buffer
    off - Offset at which to start storing characters
    len - Maximum number of characters to read
    Returns:
    The number of characters read, or -1 if the end of the stream has been reached
    Throws: IOException 
    ```

*   **int read(CharBuffer 目标):**尝试将字符读入指定的字符缓冲区。缓冲区按原样用作字符存储库:所做的唯一更改是 put 操作的结果。不执行缓冲区的翻转或倒回。

    ```java
    Syntax :public int read(CharBuffer target)
             throws IOException
    Parameters:
    target - the buffer to read characters into
    Returns:
    The number of characters added to the buffer, 
    or -1 if this source of characters is at its end
    Throws:
    IOException 
    NullPointerException
    ReadOnlyBufferException
    ```

*   **布尔就绪():**告知该流是否准备好被读取。

    ```java
    Syntax :public boolean ready()
                  throws IOException
    Returns:
    True if the next read() is guaranteed not to block for input, false otherwise. 
    Note that returning false does not guarantee that the next read will block.
    Throws:
    IOException 
    ```

*   **无效重置():**重置流。如果流已被标记，则尝试在标记处重新定位它。如果流没有被标记，那么尝试以适合特定流的方式重置它，例如通过将它重新定位到它的起点。并非所有字符输入流都支持 reset()操作，有些支持 reset()，但不支持 mark()。

    ```java
    Syntax :public void reset()
               throws IOException
    Throws:
    IOException
    ```

*   **长跳过(长 n) :** 跳过字符。此方法将一直阻塞，直到某些字符可用、出现输入/输出错误或到达流的末尾。

    ```java
    Syntax :public long skip(long n)
              throws IOException
    Parameters: n - The number of characters to skip
    Returns: The number of characters actually skipped
    Throws: IllegalArgumentException - If n is negative.
    IOException
    ```

```java
//Java program demonstrating Reader methods
import java.io.*;
import java.nio.CharBuffer;
import java.util.Arrays;
class ReaderDemo
{
    public static void main(String[] args) throws IOException
    {
        Reader r = new FileReader("file.txt");
        PrintStream out = System.out;
        char c[] = new char[10];
        CharBuffer cf = CharBuffer.wrap(c);

        //illustrating markSupported()
        if(r.markSupported()) {
            //illustrating mark()
            r.mark(100);
            out.println("mark method is supported");
        }
        //skipping 5 characters
        r.skip(5);

        //checking whether this stream is ready to be read.
        if(r.ready()) 
        {
            //illustrating read(char[] cbuf,int off,int len)
            r.read(c,0,10);
            out.println(Arrays.toString(c));

            //illustrating read(CharBuffer target )
            r.read(cf);
            out.println(Arrays.toString(cf.array()));

            //illustrating read()
            out.println((char)r.read());
        }
        //closing the stream
        r.close();
    }
}
```

**输出:**

```java
[f, g, h, i, g, k, l, m, n, o]
[p, q, r, s, t, u, v, w, x, y]
z

```

本文由 **[尼尚·夏尔马](https://www.facebook.com/ChippingEye2766)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。