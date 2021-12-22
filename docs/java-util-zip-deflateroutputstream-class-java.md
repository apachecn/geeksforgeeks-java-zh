# Java 中的 Java.util.zip .平减输出流类

> 原文:[https://www . geesforgeks . org/Java-util-zip-pinteroutputstream-class-Java/](https://www.geeksforgeeks.org/java-util-zip-deflateroutputstream-class-java/)

[Java 中的 Java.util.zip .平减计算机流类](https://www.geeksforgeeks.org/java-util-zip-deflaterinputstream-class-java/)

这个类实现了一个输出流过滤器，用于以“deflate”压缩格式压缩数据。它还被用作其他类型的压缩过滤器的基础，例如 GZIPOutputStream。
**施工人员及说明**

*   **缩减输出流(输出流输出):**使用默认压缩器和缓冲区大小创建新的输出流。
*   **缩减输出流(输出流输出，布尔同步刷新):**使用默认压缩器、默认缓冲区大小和指定的刷新模式创建新的输出流。
*   **缩减输出流(输出流输出，缩减器定义):**使用指定的压缩器和默认缓冲区大小创建新的输出流。
*   **紧缩输出流(输出流输出，紧缩定义，布尔同步刷新):**使用指定的压缩器、刷新模式和默认缓冲区大小创建新的输出流。
*   **缩减输出流(输出流输出，缩减定义，int 大小):**使用指定的压缩器和缓冲区大小创建新的输出流。
*   **紧缩输出流(输出流输出，紧缩定义，int 大小，布尔同步刷新):**使用指定的压缩器、缓冲区大小和刷新模式创建新的输出流。

**方法:**

*   **void close() :** 将剩余的压缩数据写入输出流，并关闭底层流。

    ```
    Syntax :public void close()
               throws IOException
    Overrides:
    close in class FilterOutputStream
    Throws:
    IOException
    ```

*   **受保护的 void deflate() :** 将下一个压缩数据块写入输出流。

    ```
    Syntax :protected void deflate()
                    throws IOException
    Throws:
    IOException
    ```

*   **void finish() :** 完成向输出流写入压缩数据，而不关闭底层流。

    ```
    Syntax :public void finish()
                throws IOException
    Throws:
    IOException
    ```

*   **清空冲洗():**冲洗压缩的输出流。

    ```
    Syntax :public void flush()
               throws IOException
    Overrides:
    flush in class FilterOutputStream
    Throws:
    IOException
    ```

*   **无效写入(字节[] b，int off，int len) :** 向压缩的输出流写入一个字节数组。

    ```
    Syntax :public void write(byte[] b,
             int off,
             int len)
               throws IOException
    Overrides:
    write in class FilterOutputStream
    Parameters:
    b - the data to be written
    off - the start offset of the data
    len - the length of the data
    Throws:
    IOException
    ```

*   **void write(int b) :** 向压缩的输出流中写入一个字节。

    ```
    Syntax :public void write(int b)
               throws IOException
    Overrides:
    write in class FilterOutputStream
    Parameters:
    b - the byte to be written
    Throws:
    IOException
    ```

```
//Java program to demonstrate DeflaterOutputStream

import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.IOException;
import java.util.zip.DeflaterOutputStream;

class DeflaterOutputStreamDemo
{
    public static void main(String[] args) throws IOException 
    {

        FileOutputStream fos = new FileOutputStream("file2.txt");

        //Assign FileOutputStream to DeflaterOutputStream
        DeflaterOutputStream dos = new DeflaterOutputStream(fos);

        //write it into DeflaterOutputStream
        for (int i = 0; i <10 ; i++) 
        {
            dos.write(i);
        }

        //illustrating flush() method()
        dos.flush();

        //illustrating finish()
        //Finishes writing compressed data to the output stream
        // without closing the underlying stream
        dos.finish();

        //fos is not closed
        //writing some data on file
        fos.write('G');

        //Writes remaining compressed data to the output stream
        // closes the underlying stream.
        dos.close();
    }
}
```

**注意:**由于无法在此处读取 file2.txt，因此在线 IDE 上将看不到程序的输出。

本文由 **[尼尚·夏尔马](https://www.facebook.com/ChippingEye2766)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。