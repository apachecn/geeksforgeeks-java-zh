# Java 中的 Java . io . bufferedoutstream 类

> 原文:[https://www . geesforgeks . org/Java-io-bufferedoutstream-class-Java/](https://www.geeksforgeeks.org/java-io-bufferedoutputstream-class-java/)

[Java 中的 Java.io.BufferedInputStream 类](https://www.geeksforgeeks.org/java-io-bufferedinputstream-class-java/)

Java.io.BufferedOutputStream class 类实现了一个缓冲输出流。通过设置这样的输出流，应用程序可以向底层输出流写入字节，而不必为写入的每个字节调用底层系统。

**字段**

*   **受保护字节[] buf** :存储数据的内部缓冲区。
*   **受保护的 int 计数:**缓冲区中的有效字节数。

**施工方及说明** 

*   **缓冲输出流(输出流输出):**创建一个新的缓冲输出流，将数据写入指定的底层输出流。
*   **BufferedOutputStream(OutputStream out，int size) :** 创建一个新的缓冲输出流，以指定的缓冲区大小将数据写入指定的底层输出流。

**方法:**

*   **void flush() :** 刷新该缓冲输出流。

    ```java
    Syntax :public void flush()
               throws IOException
    Overrides:
    flush in class FilterOutputStream
    Throws:
    IOException

    ```

*   **无效写入(字节[] b，int off，int len) :** 将从 offset off 开始的指定字节数组中的 len 字节写入该缓冲输出流。

    ```java
    Syntax :
    Parameters:
    b - the data.
    off - the start offset in the data.
    len - the number of bytes to write.
    Throws:
    IOException

    ```

*   **无效写入(int b) :** 将指定字节写入该缓冲输出流。

    ```java
    Syntax :
    Parameters:
    b - the byte to be written.
    Throws:
    IOException

    ```

**程序:**

```java
//Java program demonstrating BufferedOutputStream

import java.io.*;

class BufferedOutputStreamDemo
{
    public static void main(String args[])throws Exception
    {
        FileOutputStream fout = new FileOutputStream("f1.txt");

        //creating bufferdOutputStream obj
        BufferedOutputStream bout = new BufferedOutputStream(fout);

        //illustrating write() method
        for(int i = 65; i < 75; i++)
        {
            bout.write(i);
        }

        byte b[] = { 75, 76, 77, 78, 79, 80 };
        bout.write(b);

        //illustrating flush() method
        bout.flush();

        //illustrating close() method
        bout.close();
        fout.close();
    }
}
```

**输出:**

```java
ABCDEFGHIJKLMNOP
```

本文由 **[尼尚·夏尔马](https://www.facebook.com/ChippingEye2766)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。