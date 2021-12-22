# Java 中的 Java . util . zip . BulgeroutputStream 类

> 原文:[https://www . geeksforgeeks . org/Java-util-zip-duggeroutputstream-class-Java/](https://www.geeksforgeeks.org/java-util-zip-inflateroutputstream-class-java/)

这个类实现了一个输出流过滤器，用于解压缩以“deflate”压缩格式存储的数据。
**建筑商**

*   **充气输出流(输出流输出):**使用默认解压缩程序和缓冲区大小创建新的输出流。
*   **充气输出流(输出流输出，充气机输入):**使用指定的解压缩程序和默认缓冲区大小创建新的输出流。
*   **充气输出流(输出流输出，充气器输入，内部缓冲):**使用指定的解压缩程序和缓冲区大小创建新的输出流。

**方法:**

*   **void close() :** 将任何剩余的未压缩数据写入输出流，并关闭底层输出流。

    ```java
    Syntax :
    public void close()
               throws IOException
    Overrides: close in class FilterOutputStream
    Throws: IOException
    ```

*   **void finish() :** 在不关闭底层流的情况下，完成将未压缩数据写入输出流。

    ```java
    Syntax :public void finish()
                throws IOException
    Throws: IOException
    ```

*   **void flush() :** 刷新此输出流，强制写入任何挂起的缓冲输出字节。

    ```java
    Syntax :public void flush()
               throws IOException
    Overrides: flush in class FilterOutputStream
    Throws: IOException
    ```

*   **无效写入(字节[] b，int off，int len) :** 将字节数组写入未压缩的输出流。

    ```java
    Syntax :public void write(byte[] b,
             int off,
             int len)
               throws IOException
    Overrides: write in class FilterOutputStream
    Parameters: b - buffer containing compressed data to decompress and write to the output stream
    off - starting offset of the compressed data within b
    len - number of bytes to decompress from b
    Throws:
    IndexOutOfBoundsException 
    IOException
    NullPointerException 
    ZipException
    ```

*   **void write(int b) :** 向未压缩的输出流中写入一个字节。

    ```java
    Syntax :public void write(int b)
               throws IOException
    Parameters: b - a single byte of compressed data to decompress and write to the output stream
    Throws:
    IOException
    ZipException 

    ```

**程序 1**

```java
//Java program to illustrate InflaterInputStream class
import java.io.*;
import java.util.Arrays;
import java.util.zip.DeflaterInputStream;
import java.util.zip.InflaterOutputStream;

class InflaterOutputStreamDemo 
{
    public static void main(String[] args) throws IOException 
    {
        byte b[] = {1, 2, 3, 4, 5, 6};
        ByteArrayInputStream bin = new ByteArrayInputStream(b);
        DeflaterInputStream din = new DeflaterInputStream(bin);
        byte c[] = new byte[10];
        din.read(c);
        din.close();

        ByteArrayOutputStream bos = new ByteArrayOutputStream();
        InflaterOutputStream ios = new InflaterOutputStream(bos);
        //illustrating write(byte b[],int off,int len)
        ios.write(c);

        //flushing
        ios.flush();

        //Finishes writing uncompressed data to the output stream
        // without closing the underlying stream.
        ios.finish();
        System.out.println(Arrays.toString(bos.toByteArray()));
        bos.close();

        //illustrating close()
        ios.close();
    }
}
```

**输出:**

```java
[1, 2, 3, 4, 5, 6]
```

**程序 2:**

```java
//Java program to illustrate InflaterInputStream class
import java.io.*;
import java.util.Arrays;
import java.util.zip.DeflaterInputStream;
import java.util.zip.InflaterOutputStream;

class InflaterOutputStreamDemo 
{
    public static void main(String[] args) throws IOException 
    {
        byte b[] = {1, 2, 3, 4, 5, 6};
        ByteArrayInputStream bin = new ByteArrayInputStream(b);
        DeflaterInputStream din = new DeflaterInputStream(bin);
        FileOutputStream fos=new FileOutputStream("file.txt");
        byte c[] = new byte[10];
        din.read(c);
        fos.write(c);
        din.close();
        fos.close();

        //reading the compressed data
        FileInputStream fis = new FileInputStream("file.txt");

        ByteArrayOutputStream bos1=new ByteArrayOutputStream();
        InflaterOutputStream ios = new InflaterOutputStream(bos1);
        int ch;

        //illustrating write() method
        while ( (ch=fis.read() ) != -1) 
        {
            ios.write(ch);
        }
        System.out.print(Arrays.toString(bos1.toByteArray()));
    }

}
```

**输出:**

```java
[1, 2, 3, 4, 5, 6]
```

**下一篇文章:** [Java 中的 Java . util . zip . glugeringputstream 类](https://www.geeksforgeeks.org/?p=140733&preview=true)

本文由 **[尼尚·夏尔马](https://www.facebook.com/ChippingEye2766)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。