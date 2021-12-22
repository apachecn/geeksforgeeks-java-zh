# Java 中的 Java.io.FileInputStream 类

> 原文:[https://www . geesforgeks . org/Java-io-file inputstream-class-Java/](https://www.geeksforgeeks.org/java-io-fileinputstream-class-java/)

[FileInputStream 类](https://www.geeksforgeeks.org/java-io-fileinputstream-class-java/)对于以字节序列的形式从文件中读取数据非常有用。FileInputStream 用于读取原始字节流，如图像数据。要读取字符流，请考虑使用文件阅读器。

**T2**文件输入流类的构造函数

**1。文件输入流(文件文件):**创建从指定文件对象读取的输入文件流。

**2。文件输入流(文件描述符 fdobj) :** 创建从指定文件描述符读取的输入文件流。

**3。文件输入流(字符串名称):**创建输入文件流，以从具有指定名称的文件中读取。

**方法** **文件输入流类**

<figure class="table">

| way | Operations that have been performed |
| --- | --- |
| available | Returns the estimated number of remaining bytes that can be read (or skipped) from this input stream. |
| 关闭() | Close this file input stream and release any system resources associated with the stream. |
| 最终确定() | Make sure to call the close method of the file input stream when there are no more references. |
| getChannel（） | Returns the unique FileChannel object associated with this file input stream. |
| getFD() | Returns a FileDescriptor object that represents the connection to the actual file in the file system being used by this FileInputStream. |
| 已读() | Read one byte of data from this input stream. |
| 读取(*字节【】b* ) | Read up to b.length bytes of data from this input stream into a byte array. |
| 读取(*字节[] b，int off，int len* ) | Read up to len bytes of data from the input stream into the byte array. |
| 跳过() | And skips the n bytes of data in the input stream. |

</figure>

现在，当我们使用这些方法时，我们通常会按照以下步骤使用文件输入流从文件中读取数据，这是文件输入类的最终目标

**步骤 1:** 将文件附加到文件输入流，因为这将使我们能够从文件中读取数据，如下所示:

```
FileInputStream  fileInputStream =new FileInputStream(“file.txt”);
```

**步骤 2:** 现在为了从文件中读取数据，我们应该从文件输入流中读取数据，如下所示:

```
ch=fileInputStream.read();
```

**步骤 3-A:** 当没有更多数据可供进一步读取时，read()方法返回-1；

**步骤 3-B:** 那么我们应该将监视器附加到输出流上。为了显示数据，我们可以使用系统打印

```
System.out.print(ch);
```

**实施:**

*原始文件内容:*

```
This is my first line
This is my second line
```

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Demonstrate FileInputStream Class

// Importing I/O classes
import java.io.*;

// Main class
// ReadFile
class GFG {

    // Main driver method
    public static void main(String args[])
        throws IOException
    {

        // Attaching the file to FileInputStream
        FileInputStream fin
            = new FileInputStream("file1.txt");

        // Illustrating getChannel() method
        System.out.println(fin.getChannel());

        // Illustrating getFD() method
        System.out.println(fin.getFD());

        // Illustrating available method
        System.out.println("Number of remaining bytes:"
                           + fin.available());

        // llustrating skip() method
        fin.skip(4);

        // Display message for beter readability
        System.out.println("FileContents :");

        // Reading characters from FileInputStream
        // and write them
        int ch;

        // Holds true till there is data inside file
        while ((ch = fin.read()) != -1)
            System.out.print((char)ch);

        // Close the file connections
        // using close() method
        fin.close();
    }
}
```

**输出:**

```
sun.nio.ch.FileChannelImpl@1540e19d
java.io.FileDescriptor@677327b6
Number of remaining bytes:45
FileContents :
 is my first line
This is my second line
```

BufferedInputStream 可用于从文件中一次读取充满数据的缓冲区。这提高了执行速度。
本文由 [**尼尚·夏尔马**](https://www.facebook.com/ChippingEye2766?ref=bookmarks) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。