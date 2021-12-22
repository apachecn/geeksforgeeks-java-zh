# Java 中的 Java.util.zip.ZipOutputStream 类

> 原文:[https://www . geesforgeks . org/Java-util-zip-zippoutstream-class-Java/](https://www.geeksforgeeks.org/java-util-zip-zipoutputstream-class-java/)

这个类实现了一个输出流过滤器，用于以 ZIP 文件格式写入文件。包括对压缩和未压缩条目的支持。
**建造师:**

*   **压缩输出流(输出流输出):**创建新的压缩输出流。
*   **ZIP 输出流(输出流输出，字符集字符集):**创建新的 ZIP 输出流。

**方法:**

*   **void close() :** 关闭 ZIP 输出流以及正在过滤的流。

    ```java
    Syntax :public void close()
               throws IOException
    Overrides:
    close in class DeflaterOutputStream
    Throws:
    ZipException 
    IOException
    ```

*   **void closeEntry() :** 关闭当前的 ZIP 条目，并定位流以写入下一个条目。

    ```java
    Syntax :public void closeEntry()
                    throws IOException
    Throws:
    ZipException 
    IOException 
    ```

*   **void finish() :** 在不关闭底层流的情况下完成 ZIP 输出流的内容写入。当对同一输出流连续应用多个过滤器时，请使用此方法。

    ```java
    Syntax :public void finish()
                throws IOException
    Overrides:
    finish in class DeflaterOutputStream
    Throws: ZipException
    IOException
    ```

*   **void putNextEntry(zipcentry e):**开始写入一个新的 ZIP 文件条目，并将流定位到条目数据的开头。如果当前条目仍处于活动状态，则将其关闭。如果没有为条目指定压缩方法，将使用默认压缩方法，如果条目没有设置修改时间，将使用当前时间。

    ```java
    Syntax :public void putNextEntry(ZipEntry e)
                      throws IOException
    Parameters: e - the ZIP entry to be written
    Throws:
    ZipException 
    IOException
    ```

*   **作废设置注释(字符串注释):**设置 ZIP 文件注释。

    ```java
    Syntax :public void setComment(String comment)
    Parameters:
    comment - the comment string
    Throws:
    IllegalArgumentException
    ```

*   **void setLevel(int level) :** 为后续被放气的条目设置压缩级别。默认设置是 DEFAULT _ COMPRESSION。

    ```java
    Syntax :public void setLevel(int level)
    Parameters:
    level - the compression level (0-9)
    Throws:
    IllegalArgumentException
    ```

*   **void setMethod(int method):**设置后续条目的默认压缩方法。只要没有为单个 ZIP 文件条目指定压缩方法，并且最初设置为放气，就会使用此默认值。

    ```java
    Syntax :public void setMethod(int method)
    Parameters:
    method - the default compression method
    Throws: IllegalArgumentException
    ```

*   **void write(byte[] b，int off，int len)** :向当前 ZIP 条目数据写入一个字节数组。此方法将阻塞，直到所有字节都被写入。

    ```java
    Syntax :public void write(byte[] b,
             int off,
             int len)
    Parameters:
    b - the data to be written
    off - the start offset in the data
    len - the number of bytes that are written
    Throws:
    ZipException
    IOException
    ```

**程序:**

```java
//Java program demonstrating ZipOutputStream methods

import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.IOException;
import java.util.Arrays;
import java.util.zip.ZipEntry;
import java.util.zip.ZipInputStream;
import java.util.zip.ZipOutputStream;

class ZipOutputStreamDemo
{
    public static void main(String[] args) throws IOException 
    {

        FileOutputStream fos = new FileOutputStream("zipfile");
        ZipOutputStream zos = new ZipOutputStream(fos);

        //illustrating setMethod()
        zos.setMethod(8);

        //illustrating setLevel method
        zos.setLevel(5);

        ZipEntry ze1 = new ZipEntry("ZipEntry1");

        //illustrating putNextEntry method
        zos.putNextEntry(ze1);

        //illustrating setComment
        zos.setComment("This is my first comment");

        //illustrating write()
        for(int i = 0; i < 10; i++)
            zos.write(i);

        //illustrating write(byte b[], int off, int len)
        byte b[] = { 11, 12, 13};
        zos.write(b);

        //illustrating closeEntry()
        zos.closeEntry();

        //Finishes writing the contents of the ZIP output stream
        // without closing the underlying stream
        zos.finish();

        //closing the stream
        zos.close();

        FileInputStream fin = new FileInputStream("zipfile");
        ZipInputStream zin = new ZipInputStream(fin);

        //Reads the next ZIP file entry
        ZipEntry ze = zin.getNextEntry();

        //the name of the entry.
        System.out.println(ze.getName());

        //illustrating getMethod
        System.out.println(ze.getMethod());

        //Reads up to byte.length bytes of data from this input stream
        // into an array of bytes.
        byte c[] = new byte[13];

        if(zin.available() == 1)
            zin.read(c);

        System.out.print(Arrays.toString(c));

        //closes the current ZIP entry
        zin.closeEntry();

        //closing the stream
        zin.close();

    }
}
```

**输出:**

```java
ZipEntry1
8
[0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 11, 12, 13]
```

本文由 **[尼尚·夏尔马](https://www.facebook.com/ChippingEye2766)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。