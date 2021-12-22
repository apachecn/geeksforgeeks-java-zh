# Java 中的 Java.util.jar.JarInputStream 类

> 原文:[https://www . geesforgeks . org/Java-util-jar-jarinputstream-class-Java/](https://www.geeksforgeeks.org/java-util-jar-jarinputstream-class-java/)

JarInputStream 类用于从任何输入流中读取 JAR 文件的内容。它扩展了 java.util.zip.ZipInputStream 类，支持读取可选的清单条目。清单可以用来存储关于 JAR 文件及其条目的元信息。
**施工方** 

*   **JainputStream(InputStream in):**创建一个新的 JainputStream 并读取可选清单。
*   **JarInputStream(InputStream in，boolean verify) :** 创建一个新的 JarInputStream 并读取可选清单。

**方法:**

*   **受保护的 ZipEntry createZipEntry(字符串名称):**为指定的 JAR 文件条目名称创建一个新的 JAR 条目(ZipEntry)。指定 JAR 文件条目名称的清单属性将被复制到新的 JarEntry。
*   **清单 getManifest() :** 返回此 JAR 文件的清单，如果没有，则返回 null。

    ```java
    Syntax :public Manifest getManifest()
    Returns:
    the Manifest for this JAR file, or null if none.
    ```

*   **ZipEntry getNextEntry() :** 读取下一个 ZIP 文件条目，并将流定位在条目数据的开头。如果已启用验证，则在为下一个条目定位流时检测到的任何无效签名都将导致异常。

    ```java
    Syntax :public ZipEntry getNextEntry()
                          throws IOException
    Overrides: getNextEntry in class ZipInputStream
    Returns:
    the next ZIP file entry, or null if there are no more entries
    Throws:
    ZipException 
    IOException 
    SecurityException
    ```

*   **JarEntry getnext JarEntry():**读取下一个 JAR 文件条目，并将流定位在条目数据的开头。如果已启用验证，则在为下一个条目定位流时检测到的任何无效签名都将导致异常。

    ```java
    Syntax :public JarEntry getNextJarEntry()
                             throws IOException
    Returns:
    the next JAR file entry, or null if there are no more entries
    Throws:
    ZipException 
    IOException 
    SecurityException
    ```

*   **int read(byte[] b，int off，int len) :** 从当前 JAR 文件条目读取到一个字节数组中。如果 len 不为零，则该方法阻塞，直到某个输入可用；否则，不读取字节，返回 0。如果已启用验证，当前条目上的任何无效签名将在到达条目末尾之前的某个时间点报告。

    ```java
    Syntax :public int read(byte[] b,
           int off,
           int len)
             throws IOException
    Overrides: read in class ZipInputStream
    Parameters:
    b - the buffer into which the data is read
    off - the start offset in the destination array b
    len - the maximum number of bytes to read
    Returns:
    the actual number of bytes read, or -1 if the end of the entry is reached
    Throws:
    NullPointerException 
    IndexOutOfBoundsException 
    ZipException 
    IOException 
    SecurityException 
    ```

```java
//Java program demonstrating JarInputStream methods

import java.io.FileInputStream;
import java.io.IOException;
import java.io.InputStream;
import java.util.Arrays;
import java.util.jar.JarInputStream;
import java.util.zip.ZipEntry;

class JarInputStreamDemo extends JarInputStream
{

    public JarInputStreamDemo(InputStream in) throws IOException 
    {
        super(in);
    }
    public static void main(String[] args) throws IOException
    {
        FileInputStream is = new FileInputStream("codechecker.jar");
        JarInputStream jis = new JarInputStream(is);
        JarInputStreamDemo obj=new JarInputStreamDemo(jis);

        //illustrating createZipEntry() method
        ZipEntry ze1=obj.createZipEntry("ZipEntry");
        System.out.println(ze1.getName());

        //illustrating getNextEntry() method
        ZipEntry ze=jis.getNextEntry();
        System.out.println(ze.getName());

        //illustrating getManifest();
        System.out.println(jis.getManifest());

        // Reading from the current JAR file entry
        // into an array of 10 bytes
        byte b[] = new byte[10];

        //illustrating getNextJarEntry()
        //illustrating read(byte b[],int off,int length)
        while(jis.getNextJarEntry()!= null)
            jis.read(b);
        System.out.print(Arrays.toString(b));

        //closing the stream
        jis.close();
    }
}
```

**输出:**

```java
Zipentry
Attention-64.png
java.util.jar.Manifest@513ee0c5
[-119, 80, 78, 71, 13, 10, 26, 10, 0, 0]

```

本文由 **[尼尚·夏尔马](https://www.facebook.com/ChippingEye2766)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。