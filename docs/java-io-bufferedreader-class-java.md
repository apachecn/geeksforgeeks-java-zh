# Java 中的 Java . io . bufferedeeler 类

> 原文:[https://www . geesforgeks . org/Java-io-bufferedeer-class-Java/](https://www.geeksforgeeks.org/java-io-bufferedreader-class-java/)

从字符输入流中读取文本，缓冲字符以提供字符、数组和行的有效读取。

*   可以指定缓冲区大小，也可以使用默认大小。对于大多数目的来说，默认值足够大。
*   通常，读取器发出的每个读请求都会导致底层字符或字节流发出相应的读请求。
*   因此，建议在任何读操作代价可能很高的读取器(如文件读取器和输入流读取器)周围包装一个缓存器。
*   使用数据输入流进行文本输入的程序可以通过用适当的缓冲区替换每个数据输入流来进行本地化。

**施工人员:**

*   **缓冲区缓存器(Reader in) :** 创建使用默认大小的输入缓冲区的缓冲字符输入流。
*   **BufferedReader(Reader in，int sz) :** 创建使用指定大小的输入缓冲区的缓冲字符输入流。

**方法:**

*   **void close() :** 关闭流并释放与其相关联的任何系统资源。一旦流被关闭，进一步的 read()、ready()、mark()、reset()或 skip()调用将引发 IOException。关闭以前关闭的流没有效果。

    ```
    Syntax :public void close()
               throws IOException
    Throws:
    IOException
    ```

*   **空标记(int readAheadLimit) :** 标记溪流中的当前位置。对 reset()的后续调用将尝试将流重新定位到这一点。

    ```
    Syntax :public void mark(int readAheadLimit)
              throws IOException
    Parameters:
    readAheadLimit - Limit on the number of characters that may be read while still 
    preserving the mark.
    Throws:
    IllegalArgumentException - If readAheadLimit is < 0
    IOException
    ```

*   **布尔型 markSupported() :** 告诉这个流是否支持 mark()操作，它确实支持。

    ```
    Syntax :public boolean markSupported()
    Returns: true if and only if this stream supports the mark operation.
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
    这个方法实现了 Reader 类对应的 read 方法的总约定。为了方便起见，它试图通过重复调用底层流的 read 方法来读取尽可能多的字符。这种迭代读取一直持续到下列条件之一变为真:

*   已读取指定数量的字符，
*   基础流的 read 方法返回-1，表示文件结束，或者
*   基础流的 ready 方法返回 false，表示进一步的输入请求将被阻止。

如果对基础流的第一次读取返回-1 表示文件结束，则此方法返回-1。否则，此方法返回实际读取的字符数。

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
Throws:
IOException
```

*   **字符串 readLine() :** 读取一行文本。行被认为是由换行符(' \n ')、回车符(' \r ')或紧跟换行符的回车符中的任何一个结束的。

    ```
    Syntax :public String readLine()
                    throws IOException
    Returns:
    A String containing the contents of the line, not including any 
    line-termination characters, 
    or null if the end of the stream has been reached
    Throws:
    IOException
    ```

    *   **布尔就绪():**告知该流是否准备好被读取。

    ```
    Syntax :public boolean ready()
                  throws IOException
    Returns:
    True if the next read() is guaranteed not to block for input, false otherwise. 
    Note that returning false does not guarantee that the next read will block.
    Throws: IOException
    ```

    *   **无效重置():**将流重置为最近的标记。

    ```
    Syntax :public void reset()
               throws IOException
    Throws:
    IOException
    ```

    *   **long skip(long n) :** Skips characters.

    ```
    Syntax :public long skip(long n)
              throws IOException
    Parameters:
    n - The number of characters to skip
    Returns: The number of characters actually skipped
    Throws: IllegalArgumentException
    IOException
    ```

    ```
    //Java program demonstrating BufferedReader methods
    import java.io.BufferedReader;
    import java.io.FileReader;
    import java.io.IOException;
    class BufferedReaderDemo
    {
        public static void main(String[] args) throws IOException 
        {
            FileReader fr = new FileReader("file.txt");
            BufferedReader br = new BufferedReader(fr);
            char c[]=new char[20];

            //illustrating markSupported() method
            if(br.markSupported())
            {
                System.out.println("mark() method is supported");

                //illustrating mark method
                br.mark(100);
            }

            /*File Contents
            * This is first line
            this is second line
            */

            //skipping 8 characters
            br.skip(8);

            //illustrating ready() method
            if(br.ready())
            {
                //illustrating readLine() method
                System.out.println(br.readLine());

                //illustrating read(char c[],int off,int len)
                br.read(c);
                for (int i = 0; i <20 ; i++)
                {
                    System.out.print(c[i]);
                }
                System.out.println();

                //illustrating reset() method
                br.reset();
                for (int i = 0; i <8 ; i++) 
                {
                    //illustrating read() method
                    System.out.print((char)br.read());
                }
            }
        }
    }
    ```

    **输出:**

    ```
    mark() method is supported
    first line
    this is second line
    This is 
    ```

    本文由 **[尼尚·夏尔马](https://www.facebook.com/ChippingEye2766)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

    如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。