# Java 中的 Java.util.zip.ZipEntry 类

> 原文:[https://www . geesforgeks . org/Java-util-zip-zip entry-class-Java/](https://www.geeksforgeeks.org/java-util-zip-zipentry-class-java/)

这个类用于表示一个 ZIP 文件条目。
**建筑商**

*   **ZipEntry(字符串名称):**用指定的名称创建一个新的 zip 条目。
*   **邮政编码条目(邮政编码条目 e) :** 创建一个新的邮政编码条目，其字段取自指定的邮政编码条目。

**方法:**

*   **对象克隆():**返回此条目的副本。

    ```java
    Syntax :public Object clone()
    Overrides:
    clone in class Object
    Returns:
    a clone of this instance.
    ```

*   **字符串 getComment() :** 返回条目的注释字符串，如果没有，则返回 null。

    ```java
    Syntax :public String getComment()
    Returns:
    the comment string for the entry, or null if none
    ```

*   **long getCompressedSize() :** 返回压缩条目数据的大小，如果不知道则返回-1。在存储条目的情况下，压缩后的大小将与条目的未压缩大小相同。

    ```java
    Syntax :public long getCompressedSize()
    Returns:
    the size of the compressed entry data, or -1 if not known
    ```

*   **long getCrc() :** 返回未压缩条目数据的 CRC-32 校验和，如果未知，则返回-1。

    ```java
    Syntax :public long getCrc()
    Returns:
    the CRC-32 checksum of the uncompressed entry data, or -1 if not known
    ```

*   **byte[] getExtra() :** 返回条目的额外字段数据，如果没有，则返回 null。

    ```java
    Syntax :=public byte[] getExtra()
    Returns:
    the extra field data for the entry, or null if none

    ```

*   **int getMethod() :** 返回条目的压缩方法，如果未指定，则返回-1。

    ```java
    Syntax :public int getMethod()
    Returns:
    the compression method of the entry, or -1 if not specified
    ```

*   **字符串 getName() :** 返回条目的名称。

    ```java
    Syntax :public String getName()
    Returns: the name of the entry

    ```

*   **long getSize() :** 返回条目数据的未压缩大小，如果不知道，则返回-1。

    ```java
    Syntax :public long getSize()
    Returns:
    the uncompressed size of the entry data, or -1 if not know
    ```

*   **long getTime() :** 返回条目的修改时间，如果未指定则返回-1。

    ```java
    Syntax :public long getTime()
    Returns:
    the modification time of the entry, or -1 if not specified
    ```

*   **int hashCode() :** 返回该条目的哈希码值。

    ```java
    Syntax :public int hashCode()
    Overrides:
    hashCode in class Object
    Returns:
    a hash code value for this object.
    ```

*   **如果这是一个目录条目，则返回真。目录条目被定义为名称以“/”结尾的条目。

    ```java
    Syntax :public boolean isDirectory()
    Returns:
    true if this is a directory entry
    ```** 
*   **void setComment(字符串注释):**设置条目的可选注释字符串。ZIP 条目注释的最大长度为 0xffff。如果编码后指定注释字符串的长度大于 0xFFFF 字节，则只有前 0xFFFF 字节输出到 ZIP 文件条目。

    ```java
    Syntax :public void setComment(String comment)
    Parameters:
    comment - the comment string
    ```

*   **void setCompressedSize(long csize):**设置压缩条目数据的大小。

    ```java
    Syntax :public void setCompressedSize(long csize)
    Parameters:
    csize - the compressed size to set to
    ```

*   **void setCrc(长 crc) :** 设置未压缩条目数据的 CRC-32 校验和。

    ```java
    Syntax :public void setCrc(long crc)
    Parameters:
    crc - the CRC-32 value
    Throws:
    IllegalArgumentException
    ```

*   **void setExtra(字节[] extra) :** 为条目设置可选的额外字段数据。

    ```java
    Syntax :public void setExtra(byte[] extra)
    Parameters:
    extra - the extra field data bytes
    Throws:
    IllegalArgumentException
    ```

*   **void setMethod(int 方法):**设置条目的压缩方法。

    ```java
    Syntax :public void setMethod(int method)
    Parameters:
    method - the compression method, either STORED or DEFLATED
    Throws:
    IllegalArgumentException 
    ```

*   **void setSize(长尺寸):**设置条目数据的未压缩尺寸。

    ```java
    Syntax :public void setSize(long size)
    Parameters: size - the uncompressed size in bytes
    Throws:
    IllegalArgumentException 
    ```

*   **无效设置时间(长时间):**设置条目的修改时间。

    ```java
    Syntax :public void setTime(long time)
    Parameters:
    time - the entry modification time in number of milliseconds since the epoch
    ```

*   **字符串 toString() :** 返回 ZIP 条目的字符串表示形式。

    ```java
    Syntax :public String toString()
    Overrides:
    toString in class Object
    Returns:
    a string representation of the object.
    ```

**节目:** 

```java
//Java program demonstrating ZipEntry methods

import java.io.FileInputStream;
import java.io.IOException;
import java.io.PrintStream;
import java.nio.file.attribute.FileTime;
import java.util.concurrent.TimeUnit;
import java.util.zip.ZipEntry;
import java.util.zip.ZipInputStream;

class ZipEntryDemo
{
    public static void main(String[] args) throws IOException
    {
        FileInputStream fis = new FileInputStream("Awesome CV.zip");
        ZipInputStream jis = new ZipInputStream(fis);
        PrintStream cout=System.out;

        //reading the next ZIP file entry
        ZipEntry ze = jis.getNextEntry();

        //illustrating getName()
        cout.println(ze.getName());

        //illustrating getComment()
        ze.setComment("This is a comment");
        cout.println(ze.getComment());

        //illustrating setCompressedSize() and getCompressedSize()
        ze.setCompressedSize(23l);
        cout.println("CompressedSize of the entry = " + ze.getCompressedSize());

        //illustrating getSize() and setSize()
        ze.setSize(53l);
        cout.println("Size = " + ze.getSize());

        //illustrating getCrc() and setCrc()
        ze.setCrc(01);
        cout.println(ze.getCrc());

        //illustrating getMethod and setMethod
        ze.setMethod(ZipEntry.STORED);
        cout.println(ze.getMethod());

        //illustrating getCreation and setCreation()
        ze.setCreationTime(FileTime.from(10000, TimeUnit.DAYS));
        cout.println(ze.getCreationTime());

        //illustrating getLastAccessTime and setLastAccessTime
        ze.setLastAccessTime(FileTime.from(1000,TimeUnit.DAYS));
        cout.println(ze.getLastAccessTime());

        //illustrating clone()
        ZipEntry zeclone = (ZipEntry) ze.clone();
        cout.println(zeclone.getName());

        //illustrating isDirectory
        cout.println(ze.isDirectory());

        //illustrating hashcode()
        cout.println("hashcode = " + ze.hashCode());
    }
}
```

**输出:**

```java
awesome-cv.cls
This is a comment
CompressedSize of the entry = 23
Size = 53
1
0
1997-05-19T00:00:00Z
1972-09-27T00:00:00Z
awesome-cv.cls
false
hashcode = 1687382489

```

本文由 **[尼尚·夏尔马](https://www.facebook.com/ChippingEye2766)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。