# Java 中的 Java.io.SequenceInputStream in】

> 哎哎哎:# t0]https://www . geeksforgeeks . org/Java-io-sequenceinput stream-Java/

SequenceInputStream 类允许您连接多个输入流。它一个接一个地读取数据流。它从输入流的有序集合开始，从第一个开始读取，直到到达文件末尾，然后从第二个开始读取，以此类推，直到包含的最后一个输入流到达文件末尾。

**施工方及说明**

*   **SequenceInputStream(Enumeration e):**初始化一个新创建的 SequenceInputStream，它必须是一个产生类型为 InputStream 的对象的枚举。
*   **SequenceInputStream(InputStream s1，InputStream s2) :** 通过记住两个参数来初始化新创建的 SequenceInputStream，这两个参数将按顺序读取，首先是 S1，然后是 s2。

**重要方法:**

*   **读取:**从该输入流中读取下一个字节的数据。

    ```
    Syntax:
    public int read()
             throws IOException 
    Returns: the next byte of data, or -1 if the end of the stream is reached.
    Throws: IOException - if an I/O error occurs.

    ```

*   **读取(字节[] b，int off，int len) :** 从该输入流中读取多达 len 字节的数据到一个

    ```
    Syntax:
    public int read(byte[] b,
           int off,
           int len)
             throws IOException
    Overrides: read in class InputStream
    Parameters:
    b - the buffer into which the data is read.
    off - the start offset in array b at which the data is written.
    len - the maximum number of bytes read.
    Returns: int the number of bytes read.
    Throws: NullPointerException - If b is null.
    IndexOutOfBoundsException - If off is negative, len is negative, 
    or len is greater than b.length - off
    IOException - if an I/O error occurs.
    ```

    数组中
*   **可用:**返回可以从当前底层输入流读取(或跳过)的字节数的估计值，而不会被当前底层输入流的方法的下一次调用阻塞。

    ```
    Syntax :
    public int available()
                  throws IOException 
    Overrides: available in class InputStream
    Returns:an estimate of the number of bytes that can be read (or skipped over) 
    from the current underlying input stream without blocking or 0 if this input stream
    has been closed by invoking its close() method
    Throws: IOException - if an I/O error occurs.
    ```

*   **关闭:**关闭该输入流并释放与该流相关联的任何系统资源。

    ```
    Syntax :
    public void close()
               throws IOException
    Overrides: close in class InputStream
    Throws:
    IOException - if an I/O error occurs.
    ```

下面是实现一些重要方法的 SequenceInputStream 类的示例。
**程序:** 

```
//Java program to demonstrate SequenceInputStream
import java.io.*;
import java.util.*;

class SequenceISDemp
{
    public static void main(String args[])throws IOException
    {

        //creating the FileInputStream objects for all the following files
        FileInputStream fin=new FileInputStream("file1.txt");
        FileInputStream fin2=new FileInputStream("file2.txt");
        FileInputStream fin3=new FileInputStream("file3.txt");

        //adding fileinputstream obj to a vector object
        Vector v = new Vector();

        v.add(fin);
        v.add(fin2);
        v.add(fin3);

        //creating enumeration object by calling the elements method
        Enumeration enumeration = v.elements();

        //passing the enumeration object in the constructor
        SequenceInputStream sin = new SequenceInputStream(enumeration);

        // determine how many bytes are available in the first stream
        System.out.println("" + sin.available());

        // Estimating the number of bytes that can be read 
        // from the current underlying input stream 
        System.out.println( sin.available());

        int i = 0;
        while((i = sin.read())! = -1)
        {
            System.out.print((char)i);
        }
        sin.close();
        fin.close();
        fin2.close();
        fin3.close();
    }
}
```

**输出:** 

```
19
This is first file This is second file This is third file

```

注意:此程序不会在联机集成开发环境中运行，因为没有与之关联的文件。

本文由 **[尼尚·夏尔马](https://www.facebook.com/ChippingEye2766?ref=bookmarks)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。