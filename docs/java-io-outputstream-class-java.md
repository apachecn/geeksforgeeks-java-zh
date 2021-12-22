# Java 中的 Java.io.OutputStream 类

> 原文:[https://www . geesforgeks . org/Java-io-outputstream-class-Java/](https://www.geeksforgeeks.org/java-io-outputstream-class-java/)

这个抽象类是表示字节输出流的所有类的超类。输出流接受输出字节并将它们发送到某个接收器。
需要定义 OutputStream 子类的应用程序必须始终提供至少一个写入一个字节输出的方法。

**施工方及说明**

*   **输出流():**单个构造函数

**方法:**

*   **void close() :** 关闭此输出流并释放与此流关联的任何系统资源。

    ```java
    Syntax :public void close()
               throws IOException
    Throws:
    IOException
    ```

*   **void flush() :** 刷新此输出流，并强制写出任何缓冲的输出字节。

    ```java
    Syntax :public void flush()
               throws IOException
    Throws:
    IOException
    ```

*   **无效写入(字节[] b) :** 将指定字节数组中的 b.length 字节写入此输出流。

    ```java
    Syntax :public void write(byte[] b)
               throws IOException
    Parameters:
    b - the data.
    Throws:
    IOException 
    ```

*   **无效写入(字节[] b，int off，int len) :** 将从 offset off 开始的指定字节数组中的 len 字节写入此输出流。

    ```java
    Syntax :public void write(byte[] b,
             int off,
             int len)
               throws IOException
    Parameters:
    b - the data.
    off - the start offset in the data.
    len - the number of bytes to write.
    Throws:
    IOException 
    ```

*   **抽象 void write(int b) :** 将指定的字节写入该输出流。

    ```java
    Syntax :public abstract void write(int b)
                        throws IOException
    Parameters:
    b - the byte.
    Throws:
    IOException
    ```

```java
import java.io.*;
//Java program to demonstrate OutputStream
class OutputStreamDemo
{
    public static void main(String args[])throws Exception
    {
        OutputStream os = new FileOutputStream("file.txt");
        byte b[] = {65, 66, 67, 68, 69, 70};

        //illustrating write(byte[] b) method
        os.write(b);

        //illustrating flush() method
        os.flush();

        //illustrating write(int b) method
        for (int i = 71; i <75 ; i++) 
        {
            os.write(i);
        }

        os.flush();

        //close the stream
        os.close();
    }
}
```

**输出:**

```java
ABCDEFGHIJ
```

本文由 **[尼尚·夏尔马](https://www.facebook.com/ChippingEye2766?ref=bookmarks)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。