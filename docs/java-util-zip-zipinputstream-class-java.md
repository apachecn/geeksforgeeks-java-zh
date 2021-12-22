# Java 中的 Java.util.zip.ZipInputStream 类

> 原文:[https://www . geesforgeks . org/Java-util-zip-zipinputstream-class-Java/](https://www.geeksforgeeks.org/java-util-zip-zipinputstream-class-java/)

这个类实现了一个输入流过滤器，用于读取 ZIP 文件格式的文件。包括对压缩和未压缩条目的支持。
**施工人员:**

*   **ZipInputStream(InputStream in):**创建新的 ZIP 输入流。
*   **ZIPInputStream(InputStream in，Charset charset) :** 创建新的 ZIP 输入流

**方法:**

*   **int available() :** 当前条目数据达到 EOF 后返回 0，否则始终返回。
    程序不应该指望这个方法返回实际的字节数
    可以不阻塞地读取。

    ```java
    Syntax :public int available()
                  throws IOException
    Overrides:
    available in class InflaterInputStream
    Returns:
    1 before EOF and 0 after EOF has reached for current entry. 
    Programs should not count on this method to return the actual number 
    of bytes that could be read without blocking.
    Throws:
    IOException 
    ```

*   **void close() :** 关闭此输入流并释放与该流相关联的任何系统资源。

    ```java
    Syntax :public void close()
               throws IOException
    Overrides:
    close in class InflaterInputStream
    Throws: IOException
    ```

*   **void closeEntry() :** 关闭当前的 ZIP 条目，并定位流以读取下一个条目。

    ```java
    Syntax :public void closeEntry()
                    throws IOException
    Throws:
    ZipException 
    IOException 
    ```

*   **受保护的子条目创建子条目(字符串名称):**为指定的条目名称创建一个新的子条目对象。

    ```java
    Syntax :protected ZipEntry createZipEntry(String name)
    Parameters:
    name - the ZIP file entry name
    Returns:
    the ZipEntry just created
    ```

*   **ZipEntry getNextEntry() :** 读取下一个 ZIP 文件条目，并将流定位在条目数据的开头。

    ```java
    Syntax :public ZipEntry getNextEntry()
                          throws IOException
    Returns:
    the next ZIP file entry, or null if there are no more entries
    Throws:
    ZipException 
    IOException 
    ```

*   **int read(byte[] b，int off，int len) :** 从当前 ZIP 条目读取到一个字节数组中。如果 len 不为零，则该方法阻塞，直到某个输入可用；否则，不读取字节，返回 0。

    ```java
    Syntax :public int read(byte[] b,
           int off,
           int len)
             throws IOException
    Parameters:
    b - the buffer into which the data is read
    off - the start offset in the destination array b
    len - the maximum number of bytes read
    Returns:
    the actual number of bytes read, or -1 if the end of the entry is reached
    Throws:
    NullPointerException 
    IndexOutOfBoundsException 
    ZipException 
    IOException
    ```

*   **长跳过(长 n) :** 跳过当前 ZIP 条目中指定的字节数。

    ```java
    Syntax :public long skip(long n)
              throws IOException
    Parameters:
    n - the number of bytes to skip
    Returns:
    the actual number of bytes skipped
    Throws: ZipException
    IOException
    IllegalArgumentException 
    ```

```java
//Java program demonstrating ZipInputStream methods

import java.io.FileInputStream;
import java.io.IOException;
import java.io.InputStream;
import java.util.Arrays;
import java.util.jar.JarInputStream;
import java.util.zip.ZipEntry;
import java.util.zip.ZipInputStream;
class ZipInputStreamDemo extends ZipInputStream
{
    public ZipInputStreamDemo(InputStream in) 
    {
        super(in);
    }

    public static void main(String[] args) throws IOException
    {
        FileInputStream fis = new FileInputStream("Awesome CV.zip");
        ZipInputStream zis = new JarInputStream(fis);
        ZipInputStreamDemo obj = new ZipInputStreamDemo(zis);

        //illustrating createZipEntry()
        ZipEntry ze = obj.createZipEntry("ZipEntry");
        System.out.println(ze.getName());

        //illustrating getNextEntry()
        ZipEntry je = zis.getNextEntry();
        System.out.println(je.getName());

        //illustrating skip() method
        zis.skip(3);

        //illustrating closeEntry() method
        zis.closeEntry();
        zis.getNextEntry();
        byte b[] = new byte[10];

        //illustrating available() method
        //Reads up to byte.length bytes of data from this input stream
        if(zis.available() == 1)
            zis.read(b);
        System.out.println(Arrays.toString(b));

        //closing the stream
        zis.close();
    }
}
```

**输出:**

```java
ZipEntry
awesome-cv.cls
[35, 32, 65, 119, 101, 115, 111, 109, 101, 32]

```

本文由 **[尼尚·夏尔马](https://www.facebook.com/ChippingEye2766)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。