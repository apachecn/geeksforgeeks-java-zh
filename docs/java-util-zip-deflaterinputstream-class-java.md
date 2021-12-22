# Java 中的 Java.util.zip .平减计算机流类

> 原文:[https://www . geeksforgeeks . org/Java-util-zip-通缩计算机流-class-java/](https://www.geeksforgeeks.org/java-util-zip-deflaterinputstream-class-java/)

实现一个输入流过滤器，用于以“deflate”压缩格式压缩数据。

**构造函数和描述**

*   **Reduce the input stream in:** Create a new input stream using the default compressor and buffer size.
*   **InputStream in (Defl):** Create a new input stream with the specified compressor and default buffer size.
*   **InputStream in (pincher defl, int buflen):** Create a new input stream with the specified compressor and buffer size.

**方法:**

*   **int available ():** Return 0 after reaching EOF, otherwise always return 1\.

    ```java
    Syntax :public int available()
                  throws IOException
    Parameters: n - number of bytes to be skipped
    Returns:
    the actual number of bytes skipped
    Throws:
    IOException
    ```

*   **void close():** Close this input stream and its underlying input stream, and discard any pending uncompressed data.

    ```java
    Syntax :public void close()
               throws IOException
    Overrides:
    close in class FilterInputStream
    Throws: IOException
    ```

*   **Invalid flag (intlimit):** This operation is not supported.

    ```java
    Syntax :public void mark(int limit)
    Parameters:
    limit - maximum bytes that can be read before invalidating the position marker

    ```

*   **Boolean marksupported ():** always returns false because this input stream does not support the mark () and reset () methods.

    ```java
    Syntax :public boolean markSupported()
    Returns:
    false, always
    ```

*   **intread ():** Read compressed data of a single byte from the input stream.

    ```java
    Syntax :public int read()
             throws IOException
    Returns:
    a single byte of compressed data, or -1 if the end of the uncompressed
    input stream is reached
    Throws:
    IOException
    ```

*   **int read (byte [] b, int off, int len):** Read compressed data into byte array.

    ```java
    Syntax :public int read(byte[] b,
           int off,
           int len)
             throws IOException
    Parameters: b - buffer into which the data is read
    off - starting offset of the data within b
    len - maximum number of compressed bytes to read into b
    Returns:
    the actual number of bytes read, or -1 if the end of the
    uncompressed input stream is reached
    Throws: IndexOutOfBoundsException 
    IOException 
    ```

*   **Invalid reset ():** This operation is not supported.

    ```java
    Syntax :public void reset()
               throws IOException
    Throws: IOException
    ```

*   **Long skip (length n):** Skip and discard the data in the input stream.

    ```java
    Syntax :public long skip(long n)
              throws IOException
    Parameters:
    n - number of bytes to be skipped
    Returns:
    the actual number of bytes skipped
    Throws:
    IOException
    ```

    T42

**程序:**

```java
//Java program to illustrate DeflaterInputStream class
import java.io.ByteArrayInputStream;
import java.io.IOException;
import java.util.zip.DeflaterInputStream;

class DeflaterInputStreamDemo
{
    public static void main(String[] args) throws IOException
    {
        byte b[] = new byte[10];
        for (byte i = 0; i <10 ; i++)
        {
            b[i] = i;
        }
        ByteArrayInputStream bin = new ByteArrayInputStream(b);
        DeflaterInputStream din = new DeflaterInputStream(bin);

        //illustrating markSupported() method
        System.out.println(din.markSupported());

        //illustrating skip() method
        din.skip(1);

        //illustrating available() method
        System.out.println(din.available());

        //illustrating read(byte[] b,int off,int len)
        byte c[] = new byte[10];

        din.read(c,0,9);
                for (int i = 0; i < 9; i++)
        {
            System.out.print(c[i]);
        }
        while(din.available() == 1)
        {
            //Reads a single byte of compressed data
            System.out.print(din.read());
        }

        System.out.println();
        System.out.println(din.available());

        // illustrating close() method
        din.close();
    }
}
```

**输出:**

```java
false
1
-1009996100981029710199231224400175046-1
0

```

上述输出代表压缩数据。

**下一篇:** [Java 中的 Java . util . zip . pinteroutputstream 类](https://www.geeksforgeeks.org/java-util-zip-deflateroutputstream-class-java/)

本文由 **[尼尚·夏尔马](https://www.facebook.com/ChippingEye2766?ref=bookmarks)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。