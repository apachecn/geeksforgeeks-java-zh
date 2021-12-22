# Java 中的 Java.io.Writer 类

> 原文:[https://www.geeksforgeeks.org/java-io-writer-class-java-2/](https://www.geeksforgeeks.org/java-io-writer-class-java-2/)

这个抽象类用于写入字符流。子类必须实现的唯一方法是 write(char[]、int、int)、flush()和 close()。然而，大多数子类将覆盖这里定义的一些方法，以便提供更高的效率、额外的功能或两者兼而有之。
**建造师**

*   **受保护的编写器():**创建一个新的字符流编写器，其关键部分将在编写器本身上同步。
*   **受保护的编写器(对象锁):**创建一个新的字符流编写器，其关键部分将在给定的对象上同步。

**方法:**

*   **Writer append(char c) :** 将指定的字符追加到此 Writer。对表单 out.append(c)的这个方法的调用与调用
    的行为完全相同
*   **编写器追加(CharSequence csq) :** 向该编写器追加指定的字符序列。对 form out.append(csq)方法的调用与调用
    out . write(csq . toString())
    的行为完全相同，根据字符序列 csq 的 toString 规范，整个序列可能不会被追加。例如，调用字符缓冲区的 toString 方法将返回一个子序列，其内容取决于缓冲区的位置和限制。

```java
Syntax :public Writer append(CharSequence csq)
              throws IOException
Parameters:
csq - The character sequence to append. If csq is null, 
then the four characters "null" are appended to this writer.
Returns:
This writer
Throws:
IOException
```

*   **编写器追加(CharSequence csq，int start，int end) :** 向该编写器追加指定字符序列的子序列。将指定字符序列的子序列附加到该书写器

    ```java
    Syntax :public Writer append(CharSequence csq,
                int start,
                int end)
                  throws IOException
    Parameters:
    csq - The character sequence from which a subsequence will be appended. 
    If csq is null, then characters will be appended as 
    if csq contained the four characters "null".
    start - The index of the first character in the subsequence
    end - The index of the character following the last character in the subsequence
    Returns: This writer
    Throws:
    IndexOutOfBoundsException
    IOException
    ```

    *   **抽象虚空关闭():**关闭溪流，先冲洗。一旦流被关闭，进一步的 write()或 flush()调用将导致引发 IOException。关闭以前关闭的流没有效果。

    ```java
    Syntax :public abstract void close()
                        throws IOException
    Throws:
    IOException 
    ```

    *   **抽象虚空冲():**冲溪。如果流已将各种 write()方法中的任何字符保存在缓冲区中，请立即将它们写入预期目标。然后，如果目的地是另一个字符或字节流，则刷新它。因此，一个 flush()调用将刷新一系列写入器和输出流中的所有缓冲区。

    ```java
    Syntax :public abstract void flush()
                        throws IOException
    Throws:
    IOException
    ```

    *   **void write(char[] cbuf) :** 写入字符数组。

    ```java
    Syntax :public void write(char[] cbuf)
               throws IOException
    Parameters:
    cbuf - Array of characters to be written
    Throws:
    IOException - If an I/O error occurs
    ```

    *   **抽象 void write(char[] cbuf，int off，int len) :** 写入字符数组的一部分。

    ```java
    Syntax :public abstract void write(char[] cbuf,
             int off,
             int len)
                        throws IOException
    Parameters:
    cbuf - Array of characters
    off - Offset from which to start writing characters
    len - Number of characters to write
    Throws:
    IOException
    ```

    *   **void write(int c) :** 写单个字符。要写入的字符包含在给定整数值的 16 个低位中；16 个高位被忽略。
    想要支持高效单字符输出的子类应该覆盖这个方法。

    ```java
    Syntax :public void write(int c)
               throws IOException
    Parameters:
    c - int specifying a character to be written
    Throws:
    IOException
    ```

    *   **空写(字符串):**写字符串。

    ```java
    Syntax :public void write(String str)
               throws IOException
    Parameters:
    str - String to be written
    Throws: IOException
    ```

    *   **void write(String str, int off, int len) :** Writes a portion of a string.

    ```java
    Syntax :public void write(String str,
             int off,
             int len)
               throws IOException
    Parameters:
    str - A String
    off - Offset from which to start writing characters
    len - Number of characters to write
    Throws:
    IndexOutOfBoundsException 
    ```

    **程序:**

    ```java
    //Java program demonstrating Writer methods

    import java.io.IOException;
    import java.io.PrintWriter;
    import java.io.Writer;
    class WriterDemo
    {
        public static void main(String[] args) throws IOException
        {
            Writer wr=new PrintWriter(System.out);
            char c[] = {'B','C','D','E','F'};
            CharSequence cs = "JKL";
            String str = "GHI";

            //illustrating write(int c)
            wr.write(65);

            //flushing the stream
            wr.flush();

            //illustrating write(char[] c,int off,int len)
            wr.write(c);
            wr.flush();

            //illustrating write(String str,int off,int len)
            wr.write(str);
            wr.flush();

            //illustrating append(Charsequence cs,int start,int end)
            wr.append(cs);
            wr.flush();

            //illustrating append(int ch)
            wr.append('M');
            wr.flush();

            //closing the stream
            wr.close();
        }
    }
    ```

    **输出:**

    ```java
    ABCDEFGHIJKLM
    ```

    本文由 **[尼尚·夏尔马](https://www.facebook.com/ChippingEye2766)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

    如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。