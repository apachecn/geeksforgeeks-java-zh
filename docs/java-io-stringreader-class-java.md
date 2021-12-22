# Java 中的 Java.io.StringReader 类

> 原文:[https://www . geesforgeks . org/Java-io-string reader-class-Java/](https://www.geeksforgeeks.org/java-io-stringreader-class-java/)

这是一个字符流类，其来源是一个字符串。
**建造师:**

*   **StringReader(String s) :** Creates a new string reader.

    **方法:**

    *   **void close() :** 关闭流并释放与其相关联的任何系统资源。一旦流被关闭，进一步的 read()、ready()、mark()或 reset()调用将引发 IOException。关闭以前关闭的流没有效果。

        ```java
        Syntax :public void close()

        ```

    *   **空标记(int readAheadLimit) :** 标记溪流中的当前位置。对 reset()的后续调用会将流重新定位到这一点。

        ```java
        Syntax :public void mark(int readAheadLimit)
                  throws IOException
        Parameters: readAheadLimit - Limit on the number of characters that may 
        be read while still preserving the mark. Because the stream's input 
        comes from a string, there is no actual limit, so this argument 
        must not be negative, but is otherwise ignored.
        Throws:
        IllegalArgumentException
        IOException
        ```

    *   **布尔型 markSupported() :** 告诉这个流是否支持 mark()操作，它确实支持。

        ```java
        Syntax :public boolean markSupported()
        Returns:
        true if and only if this stream supports the mark operation.
        ```

    *   **int read() :** 读取单个字符。

        ```java
        Syntax :public int read()
                 throws IOException
        Returns:
        The character read, or -1 if the end of the stream has been reached
        Throws:
        IOException
        ```

    *   **int read(char[] cbuf，int off，int len) :** 将字符读入数组的一部分。

        ```java
        Syntax :public int read(char[] cbuf,
               int off,
               int len)
                 throws IOException
        Parameters:
        cbuf - Destination buffer
        off - Offset at which to start writing characters
        len - Maximum number of characters to read
        Returns:
        The number of characters read, or -1 if the end of the stream has been reached
        Throws:
        IOException
        ```

    *   **布尔就绪():**告知该流是否准备好被读取。

        ```java
        Syntax :public boolean ready()
                      throws IOException
        Returns:
        True if the next read() is guaranteed not to block for input
        Throws:
        IOException
        ```

    *   **void reset() :** 将流重置为最近的标记，如果从未标记过，则重置为字符串的开头。

        ```java
        Syntax :public void reset()
                   throws IOException
        Throws: IOException 
        ```

    *   **long skip(long ns) :** Skips the specified number of characters in the stream.. Returns the number of characters that were skipped.
        The ns parameter may be negative, even though the skip method of the Reader superclass throws an exception in this case. Negative values of ns cause the stream to skip backwards. Negative return values indicate a skip backwards. It is not possible to skip backwards past the beginning of the string.

        如果已经读取或跳过了整个字符串，则此方法不起作用，并且始终返回 0。

        ```java
        Syntax :public long skip(long ns)
                  throws IOException
        Parameters:
        ns - The number of characters to skip
        Returns:
        The number of characters actually skipped
        Throws: IOException
        ```

    **程序:**

    ```java
    //Java program demonstrating StringReader methods
    import java.io.IOException;
    import java.io.StringReader;
    class StringReaderDemo
    {
        public static void main(String[] args) throws IOException
        {
            StringReader str = new StringReader("GeeksforGeeks");
            char c[]=new char[7];

            //illustrating markSupported()
            if(str.markSupported())
            {
                System.out.println("Mark method is supported");
                // illustrating mark()
                str.mark(100);
            }

            //illustrating skip() method
            str.skip(5);

            //whether this stream is ready to be read.
            if(str.ready())
            {
                //illustrating read() method
                System.out.print((char)str.read());

                //illustrating read(char cff[],int off,int len)
                str.read(c);
                for (int i = 0; i <7 ; i++) 
                {
                    System.out.print(c[i]);
                }
            }

            //illustrating reset() method
            str.reset();

            for (int i = 0; i < 5; i++) 
            {
                System.out.print((char)str.read());
            }

            //illustrating close()
            str.close();
        }
    }
    ```

    **输出:**

    ```java
    Mark method is supported
    forGeeksGeeks
    ```

    本文由 **[尼尚·夏尔马](https://www.facebook.com/ChippingEye2766)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

    如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。