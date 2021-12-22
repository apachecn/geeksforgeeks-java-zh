# Java 中的 Java.util.zip.GZIPInputStream 类

> 原文:[https://www . geesforgeks . org/Java-util-zip-gzipinputstream-class-Java/](https://www.geeksforgeeks.org/java-util-zip-gzipinputstream-class-java/)

这个类实现了一个流过滤器，用于读取 GZIP 文件格式的压缩数据。

**施工人员**

*   **GZipInputStream(InputStream in):**使用默认缓冲区大小创建新的输入流。
*   **GZipInputStream(InputStream in，int size) :** 用指定的缓冲区大小创建新的输入流。

**方法:**

*   **void close() :** 关闭此输入流并释放与该流相关联的任何系统资源。

    ```
    Syntax :public void close()
               throws IOException
    Specified by:
    close in interface Closeable
    Specified by:
    close in interface AutoCloseable
    Overrides:
    close in class InflaterInputStream
    Throws:
    IOException 
    ```

*   **int read(byte[] buf，int off，int len) :** 将未压缩的数据读入字节数组。如果 len 不为零，该方法将阻塞，直到某些输入可以解压缩；否则，不读取字节，返回 0。

    ```
    Syntax :public int read(byte[] buf,
           int off,
           int len)
             throws IOException
    Overrides:
    read in class InflaterInputStream
    Parameters: buf - the buffer into which the data is read
    off - the start offset in the destination array b
    len - the maximum number of bytes read
    Returns:
    the actual number of bytes read, or -1 if the end of the
    compressed input stream is reached
    Throws:
    NullPointerException
    IndexOutOfBoundsException
    ZipException
    IOException 
    ```

**从类 Java . util . zip . influgerinputstream 继承的方法**
可用、填充、标记、标记支持、读取、重置、跳过
**从类 java.io.FilterInputStream 继承的方法**
读取
**从类 java.lang.Object 继承的方法**
克隆、等于、finalize、getClass、hashCode、notifyAll、toString、等待、等待

**程序:**

```

//Java program demonstrating GZipInputStream methods 

import java.io.FileInputStream;              
import java.io.FileOutputStream;     
import java.io.IOException;              
import java.util.Arrays;
import java.util.zip.GZIPInputStream; 

class GZipInputStreamDemo        
{                                                                            
    public static void main(String[] args) throws IOException 
    {                                                                                            
        FileInputStream fis = new FileInputStream("file.txt"); 
        GZIPInputStream gzis = new GZIPInputStream(fis);    

        //Uncompressed FileContents      
        //01234567890 
        byte b[]=new byte[10];

        //skipping 1 byte    
        gzis.skip(1);

        //illustrating available() and 
        //read(byte b[],int off,int len) 
        if( gzis.available()!=-1)    
            gzis.read(b);                    
        System.out.println(Arrays.toString(b));

        //closing the stream                                                 
        gzis.close();                                                        
    }                                                                        
} 
```

**输出:**

```
[1, 2, 3, 4, 5, 6, 7, 8, 9, 0]
```

本文由 **[尼尚·夏尔马](https://www.facebook.com/ChippingEye2766)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。