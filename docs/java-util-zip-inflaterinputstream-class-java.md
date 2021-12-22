# Java 中的 Java . util . zip . BuggerInputStream 类

> 原文:[https://www . geeksforgeeks . org/Java-util-zip-充气机计算机流-class-java/](https://www.geeksforgeeks.org/java-util-zip-inflaterinputstream-class-java/)

这个类实现了一个流过滤器，用于以“deflate”压缩格式解压缩数据。它还被用作其他解压缩过滤器的基础，如 GZIPInputStream。
**建筑商**

*   **用默认的解压缩程序和缓冲区大小创建一个新的输入流。**
*   **充气输入流(InputStream in，Fluger INF):**使用指定的解压缩程序和默认缓冲区大小创建新的输入流。
*   **充气输入流(InputStream in，Fluger INF，int size) :** 用指定的解压缩程序和缓冲区大小创建一个新的输入流。

**方法:**

*   **int available() :** 达到 EOF 后返回 0，否则总是返回 1。

    ```
    Syntax : public int available()
                  throws IOException
    Returns:
    1 before EOF and 0 after EOF.
    Throws:
    IOException

    ```

*   **void close() :** 关闭此输入流并释放与该流相关联的任何系统资源。

    ```
    Syntax : public void close()
               throws IOException
    Throws:
    IOException 

    ```

*   **受保护的空白填充():**用更多要解压缩的数据填充输入缓冲区。

    ```
    Syntax : protected void fill()
                 throws IOException
    Throws: IOException

    ```

*   **无效标记(int readlimit) :** 标记该输入流中的当前位置。

    ```
    Syntax : public void mark(int readlimit)
    Parameters:
    readlimit - the maximum limit of bytes that can be read
    before the mark position becomes invalid.
    ```

*   **布尔标记支持():**测试该输入流是否支持标记和重置方法。

    ```
    Syntax : public boolean markSupported()
    Returns:
    a boolean indicating if this stream type supports the mark and reset methods.

    ```

*   **int read() :** 读取一个字节的未压缩数据。

    ```
    Syntax : public int read()
             throws IOException
    Returns: the byte read, or -1 if end of compressed input is reached
    Throws:
    IOException
    ```

*   **int read(byte[] b，int off，int len) :** 将未压缩的数据读入字节数组。

    ```
    Syntax : public int read(byte[] b,
           int off,
           int len)
             throws IOException
    Parameters: b - the buffer into which the data is read
    off - the start offset in the destination array b
    len - the maximum number of bytes read
    Returns: the actual number of bytes read, or -1 if the end of the compressed input is reached.
    Throws:
    NullPointerException 
    IndexOutOfBoundsException 
    ZipException
    IOException

    ```

*   **void reset() :** 将此流重新定位到上次在此输入流上调用 mark 方法时的位置。

    ```
    Syntax : public void reset()
               throws IOException
    Throws:
    IOException

    ```

*   **长跳过(长 n) :** 跳过指定数量的未压缩数据字节。

    ```
    Syntax : public long skip(long n)
              throws IOException
    Parameters:
    n - the number of bytes to skip
    Returns:
    the actual number of bytes skipped.
    Throws:
    IOException 
    IllegalArgumentException 
    ```

**程序:**

```
//Java program to demonstrate InflaterInputStream
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.IOException;
import java.util.zip.DeflaterOutputStream;
import java.util.zip.InflaterInputStream;

class InflaterInputStreamDemo
{
    public static void main(String[] args) throws IOException
    {

        FileOutputStream fos = new FileOutputStream("file.txt");

        //Assign FileOutputStream to DeflaterOutputStream
        DeflaterOutputStream dos = new DeflaterOutputStream(fos);

        //write it into DeflaterOutputStream
        for (int i = 0; i < 10; i++)
        {
            dos.write(i);
        }
        dos.flush();
        dos.close();
        FileInputStream fis = new FileInputStream("file.txt");
        InflaterInputStream iis = new InflaterInputStream(fis);

        //illustrating available() method
        System.out.println(iis.available());

        //illustrating mark and markSupported()
        if (iis.markSupported())
            iis.mark(15);
        else
            System.out.println(false);

        //illustrating skip() method
        iis.skip(3);

        //illustrating read()
        for (int i = 0; i <3 ; i++) 
        {
            System.out.print(iis.read());
        }

        //illustrating read(byte[] b,int off,int len)
        byte b[]=new byte[4];

        for (int i = 0; i <4 ; i++) 
        {
            iis.read(b,0,4);
        }

        for (int i = 0; i < 4; i++) 
        {
            System.out.print(b[i]);
        }
    }
}
```

**输出:**

```
1
false
3456789
```

 **下一篇文章:** [Java 中的 Java . util . zip . uggeroutputstream 类](https://www.geeksforgeeks.org/java-util-zip-inflateroutputstream-class-java/)

本文由 **[尼尚·夏尔马](https://www.facebook.com/ChippingEye2766)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。