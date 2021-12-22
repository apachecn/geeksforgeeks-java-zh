# 使用 Java 中的文件流复制文件

> 原文:[https://www . geesforgeks . org/copy-file-use-filestreams-Java/](https://www.geeksforgeeks.org/copy-file-using-filestreams-java/)

我们可以使用 Java 中的文件输入流和文件输出流类将文件从一个位置复制到另一个位置。
为此我们必须导入一些 java.io 包的特定类。例如，让我们用 import java.io.*语句包含整个包；

复制文件的主要逻辑是读取与 FileInputStream 变量关联的文件，并将读取的内容写入与 FileOutputStream 变量关联的文件。

**程序中使用的方法**

1.  **int read()**；读取一字节数据。存在于文件输入流中。这个方法的其他版本:int read(byte[] bytearray)和 int read(byte[] bytearray，int offset，int length)
2.  **void write(int b)** :写入一个字节的数据。出现在文件输出流中。此方法的其他版本:void write(byte[] bytearray)和 void write(byte[] bytearray，int offset，int length)；

```
/* Program to copy a src file to destination.
   The name of src file and dest file must be
   provided using command line arguments where
   args[0] is the name of source file and
   args[1] is name of destination file */

import java.io.*;
class src2dest
{
    public static void main(String args[])
    throws FileNotFoundException,IOException
    {
        /* If file doesnot exist FileInputStream throws
           FileNotFoundException and read() write() throws
           IOException if I/O error occurs */
        FileInputStream fis = new FileInputStream(args[0]);

        /* assuming that the file exists and need not to be
           checked */
        FileOutputStream fos = new FileOutputStream(args[1]);

        int b;
        while  ((b=fis.read()) != -1)
            fos.write(b);

        /* read() will readonly next int so we used while
           loop here in order to read upto end of file and
           keep writing the read int into dest file */
        fis.close();
        fos.close();
    }
}
```

本文由**帕鲁尔当**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。