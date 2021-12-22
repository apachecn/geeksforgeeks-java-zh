# Java 中的字符流 Vs 字节流

> 原文:[https://www . geesforgeks . org/character-stream-vs-byte-stream-Java/](https://www.geeksforgeeks.org/character-stream-vs-byte-stream-java/)

**输入输出流**

流是一种顺序访问文件的方法。输入/输出流是指代表不同类型源(如磁盘文件)的输入源或输出目的地。java.io 包提供了允许您在 Unicode 字符流和非 Unicode 文本的字节流之间进行转换的类。

**流**–数据序列。
**输入流:**从源读取数据。
**输出流:**将数据写入目的地。

**字符流**

在 Java 中，字符是使用 Unicode 约定存储的(详情参见[这个](https://docs.oracle.com/javase/tutorial/java/data/characters.html))。字符流自动允许我们逐个字符地读/写数据。例如，文件读取器和文件写入器是用于从源读取和向目标写入的字符流。
T3】

```java
// Java Program illustrating that we can read a file in
// a human readable format using FileReader
import java.io.*;   // Accessing FileReader, FileWriter, IOException
public class GfG
{
    public static void main(String[] args) throws IOException
    {
        FileReader sourceStream = null;
        try 
        {
            sourceStream = new FileReader("test.txt");

            // Reading sourcefile and writing content to 
            // target file character by character. 
            int temp;
            while ((temp = sourceStream.read()) != -1)
                 System.out.println((char)temp);
        }
        finally 
        {            
            // Closing stream as no longer in use 
            if (sourceStream != null)            
                sourceStream.close();         
        }
    }
}
```

输出:

```java
Shows contents of file test.txt 
```

**字节流**

字节流逐字节(8 位)处理数据。例如，文件输入流用于从源读取，文件输出流用于写入目标。

```java
// Java Program illustrating the Byte Stream to copy 
// contents of one file to another file.
import java.io.*;   
public class BStream
{
    public static void main(String[] args) throws IOException
    {
        FileInputStream sourceStream = null;
        FileOutputStream targetStream = null;

        try 
        {
            sourceStream = new FileInputStream("sorcefile.txt");
            targetStream = new FileOutputStream ("targetfile.txt");

            // Reading source file and writing content to target
            // file byte by byte
            int temp;
            while ((temp = sourceStream.read()) != -1)
                targetStream.write((byte)temp);            
        }
        finally 
        {
            if (sourceStream != null)
                sourceStream.close();            
            if (targetStream != null)            
                targetStream.close();            
        }
    }
}
```

**什么时候使用字符流而不是字节流？**

*   在 Java 中，字符是使用 Unicode 约定存储的。当我们想要处理文本文件时，字符流非常有用。这些文本文件可以逐字符处理。字符大小通常为 16 位。

**什么时候使用字节流而不是字符流？**

*   面向字节的读取逐字节进行。字节流适用于处理原始数据，如二进制文件。

**备注:**

*   字符流的名称通常以读取器/写入器结尾，字节流的名称以输入流/输出流结尾
*   示例代码中使用的流是非缓冲流，效率较低。为了提高效率，我们通常将它们与缓冲读取器/写入器一起使用。我们将很快讨论使用 BufferedReader/BufferedWriter(用于字符流)和 BufferedInputStream/bufferedoutstream(用于字节流)类。
*   如果不再使用该流，建议将其关闭。这确保了如果发生任何错误，流不会受到影响。
*   由于文件可能不存在，上述代码可能无法在在线编译器中运行。

本文由**莫希特·古普塔**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。