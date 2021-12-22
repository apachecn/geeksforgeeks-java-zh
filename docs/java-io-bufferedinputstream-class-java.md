# Java 中的 Java.io.BufferedInputStream 类

> 原文:[https://www . geesforgeks . org/Java-io-bufferedinputstream-class-Java/](https://www.geeksforgeeks.org/java-io-bufferedinputstream-class-java/)

缓冲输入流向另一个输入流添加功能，即缓冲输入并支持标记和重置方法的能力。创建缓冲区输入流时，会创建一个内部缓冲区数组。当读取或跳过流中的字节时，根据需要从包含的输入流中重新填充内部缓冲区，一次填充许多字节。

**施工方及说明** 

*   **BufferedInputStream(InputStream in):**创建一个 BufferedInputStream，并将其参数(输入流)保存在中，以备后用。
*   **BufferedInputStream(InputStream in，int size) :** 创建一个具有指定缓冲区大小的 BufferedInputStream，并将其参数输入流保存在中，以备后用。

**方法:**

*   **int available() :** 返回
    可以从该输入流中读取(或跳过)的字节数的估计值，而不会被该输入流的方法的下一次调用所阻塞。

```
Syntax:public int available()
              throws IOException
Returns: an estimate of the number of bytes that can be 
read (or skipped over) from this input stream without blocking.
Throws:
IOException

```

*   **void close() :** 关闭此输入流并释放与该流相关联的任何系统资源。

    ```
    Syntax:public void close()
               throws IOException
    Overrides: close in class FilterInputStream
    Throws:
    IOException 

    ```

    *   **无效标记(int readlimit) :** 标记该输入流中的当前位置。

    ```
    Syntax:public void mark(int readlimit)
    Overrides:
    mark in class FilterInputStream
    Parameters:
    readlimit - the maximum limit of bytes that can be read 
    before the mark position becomes invalid.

    ```

    *   **布尔标记支持():**测试该输入流是否支持标记和重置方法。

    ```
    Syntax:public boolean markSupported()
    Overrides:
    markSupported in class FilterInputStream
    Returns: a boolean indicating if this stream type supports the mark and reset methods.

    ```

    *   **int read() :** 从输入流中读取下一个字节的数据。

    ```
    Syntax:public int read()
             throws IOException
    Returns: the next byte of data, or -1 if the end of the stream is reached.
    Throws:
    IOException 

    ```

    *   **int read(byte[] b，int off，int len) :** 从给定的偏移量开始，将该字节输入流中的字节读入指定的字节数组。

    ```
    Syntax:public int read(byte[] b,
           int off,
           int len)
             throws IOException
    Parameters:
    b - destination buffer.
    off - offset at which to start storing bytes.
    len - maximum number of bytes to read.
    Returns:
    the number of bytes read, or -1 if the end of the stream has been reached.
    Throws:
    IOException 

    ```

    *   **void reset() :** 将此流重新定位到上次在此输入流上调用 mark 方法时的位置。

    ```
    Syntax:public void reset()
               throws IOException
    Overrides:
    reset in class FilterInputStream
    Throws:
    IOException

    ```

    *   **long skip(long n) :**Skips over and discards n bytes of data from this input stream

    ```
    Syntax:public long skip(long n)
              throws IOException
    Parameters: n - the number of bytes to be skipped.
    Returns:
    the actual number of bytes skipped.
    Throws:
    IOException
    ```

    **程序:**

    ```
    // Java program to demonstrate working of BufferedInputStream
    import java.io.BufferedInputStream;
    import java.io.FileInputStream;
    import java.io.IOException;

    // Java program to demonstrate BufferedInputStream methods
    class BufferedInputStreamDemo
    {
        public static void main(String args[]) throws IOException
        {
            // attach the file to FileInputStream
            FileInputStream fin = new FileInputStream("file1.txt");

            BufferedInputStream bin = new BufferedInputStream(fin);

            // illustrating available method
            System.out.println("Number of remaining bytes:" +
                                                bin.available());

            // illustrating markSupported() and mark() method
            boolean b=bin.markSupported();
            if (b)
                bin.mark(bin.available());

            // illustrating skip method
            /*Original File content:
            * This is my first line
            * This is my second line*/
            bin.skip(4);
            System.out.println("FileContents :");

            // read characters from FileInputStream and
            // write them
            int ch;
            while ((ch=bin.read()) != -1)
                System.out.print((char)ch);

            // illustrating reset() method
            bin.reset();
            while ((ch=bin.read()) != -1)
                System.out.print((char)ch);

            // close the file
            fin.close();
        }
    }
    ```

    输出:

    ```
    Number of remaining bytes:47
    FileContents :
     is my first line
    This is my second line
    This is my first line
    This is my second line
    ```

     **下一篇:** [Java 中的 Java . io . bufferedoutstream 类](https://www.geeksforgeeks.org/java-io-bufferedoutputstream-class-java/)

    本文由 **[尼尚·夏尔马](https://www.facebook.com/ChippingEye2766?ref=bookmarks)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

    如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。