# Java 中的 Java.io.FilterReader 类

> 原文:[https://www . geesforgeks . org/Java-io-filter reader-class-Java/](https://www.geeksforgeeks.org/java-io-filterreader-class-java/)

用于读取过滤字符流的抽象类。抽象类 FilterReader 本身提供默认方法，将所有请求传递给包含的流。FilterReader 的子类应该覆盖这些方法中的一些，并且还可以提供额外的方法和字段。
**建造师:**

*   **受保护的筛选读取器(读取器 in)** :创建新的筛选读取器。

**方法:**

*   **void close() :** 关闭流并释放与其相关联的任何系统资源。一旦流被关闭，进一步的 read()、ready()、mark()、reset()或 skip()调用将引发 IOException。关闭以前关闭的流没有效果。

    ```
    Syntax :public void close()
               throws IOException
    Throws:
    IOException
    ```

*   **空标记(int readAheadLimit) :** 标记溪流中的当前位置。

    ```
    Syntax :public void mark(int readAheadLimit)
              throws IOException
    Parameters:
    readAheadLimit - Limit on the number of characters that may be read 
    while still preserving the mark. After reading this many characters,
     attempting to reset the stream may fail.
    Throws:
    IOException
    ```

*   **布尔型 markSupported() :** 告知此流是否支持 mark()操作。

    ```
    Syntax :public boolean markSupported()
    Returns:
    true if and only if this stream supports the mark operation.
    ```

*   **int read() :** 读取单个字符。

    ```
    Syntax :public int read()
             throws IOException
    Returns: The character read, as an integer in the range 0 to 65535 (0x00-0xffff), 
    or -1 if the end of the stream has been reached
    Throws:
    IOException
    ```

*   **int read(char[] cbuf，int off，int len) :** 将字符读入数组的一部分。

    ```
    Syntax :public int read(char[] cbuf,
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

*   **布尔就绪():**告知该流是否准备好被读取。

    ```
    Syntax :public boolean ready()
                  throws IOException
    Returns:
    True if the next read() is guaranteed not to block for input, 
    false otherwise. Note that returning false does not guarantee
    that the next read will block.
    Throws: IOException
    ```

*   **无效重置():**重置流。

    ```
    Syntax :public void reset()
               throws IOException
    Throws:
    IOException
    ```

*   **长跳过(长 n) :** 跳过字符。

    ```
    Syntax :public long skip(long n)
              throws IOException
    Parameters:
    n - The number of characters to skip
    Returns:
    The number of characters actually skipped
    Throws:
    IOException
    ```

**程序:**

```
//Java program illustrating FilterReader class methods

import java.io.*;
class FilterReaderdemo
{
    public static void main(String[] args) throws IOException
    {
        Reader r = new StringReader("GeeksforGeeks");
        FilterReader fr = new FilterReader(r) 
        {
        };
        char ch[] = new char[8];

        //illustrating markSupported()
        if(fr.markSupported())
        {
            //illustrating mark() method
            System.out.println("mark method is supported");
            fr.mark(100);
        }

        //illustrating skip() method
        fr.skip(5);

        //illustrating ready()
        if(fr.ready())
        {
            //illustrating read(char[] cbuff,int off,int len)
            fr.read(ch);
            for (int i = 0; i < 8; i++) 
            {
                System.out.print(ch[i]);
            }

            //illustrating reset()
            fr.reset();
            for (int i = 0; i <5 ; i++)
            {
                //illustrating read()
                System.out.print((char)fr.read());
            }
        }

        //closing the stream
        fr.close();
    }
}
```

**输出:**

```
mark method is supported
forGeeksGeeks
```

本文由 **[尼尚·夏尔马](https://www.facebook.com/ChippingEye2766)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。