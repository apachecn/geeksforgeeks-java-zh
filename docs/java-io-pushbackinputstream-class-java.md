# Java 中的 Java . io . pubackinputstream 类

> 原文:[https://www . geesforgeks . org/Java-io-pubackinputstream-class-Java/](https://www.geeksforgeeks.org/java-io-pushbackinputstream-class-java/)

推回用于输入流，允许读取一个字节，然后将其返回(即“推回”)到流中。推回输入流类实现了这个想法。它提供了一种在不中断输入流的情况下“窥视”输入流的机制。
它扩展了 FilterInputStream。

**字段:**

*   **受保护字节[] buf** :这是推回缓冲区。*   **受保护的 int 位置**–这是推回缓冲区内的位置，下一个字节将从该位置读取。*   **protected InputStream in** – This is the input stream to be filtered.

    **施工人员:**

    *   **推回输入流(输入流 in):** 这将创建一个流对象，允许向输入流返回一个字节。*   **PushbackInputStream(InputStream in, int numBytes):** This creates a stream that has a pushback buffer that is numBytes long. This allows multiple bytes to be returned to the input stream.

    **方法:**

    1.  **int available():** 返回可以从此输入流读取(或跳过)的字节数的估计值，而不会被此输入流的方法的下一次调用阻塞。下一次调用可能是同一个线程或另一个线程。单次读取或跳过这么多字节不会阻塞，但可能会读取或跳过更少的字节。

        ```
        Syntax: public int available()
        Returns: the number of bytes that can be read
         (or skipped over) from the input stream without blocking.
        Exception: IOException - if this input stream has 
        been closed by invoking its close() method, or an I/O error occurs.

        ```

    2.  **void close():** 关闭此输入流并释放与该流相关联的任何系统资源。一旦流被关闭，进一步的 read()、unread()、available()、reset()或 skip()调用将引发 IOException。关闭以前关闭的流没有效果。

        ```
        Syntax: public void close()
        Returns: NA
        Exception: IOException - if an I/O error occurs.

        ```

    3.  **布尔标记支持():**测试该输入流是否支持标记和重置方法，但它不支持。

        ```
        Syntax: public boolean markSupported()
        Returns: false, since this class does not support the mark and reset methods.
        Exception: NA

        ```

        ## 爪哇语言（一种计算机语言,尤用于创建网站)

        ```
        // Java code illustrating available(), close() 
        // and markSupported() methods

        import java.io.ByteArrayInputStream;
        import java.io.IOException;
        import java.io.PrintWriter;
        import java.io.PushbackInputStream;

        public class PushbackInputStreamDemo 
        {
            public static void main(String arg[]) throws IOException
            {
                PrintWriter pw = new PrintWriter(System.out, true);
                String str = "Hey geeks ";
                byte b[] = str.getBytes();
                ByteArrayInputStream bout = new ByteArrayInputStream(b);
                PushbackInputStream push = new PushbackInputStream(bout);

                // checking no. of bytes available
                pw.println("available bytes: " + push.available());

                // checking if mark is supported
                pw.println("mark supported? :" + push.markSupported());

                pw.close();
            }
        }
        ```

        输出:

        ```
        available bytes: 10
        mark supported? :false

        ```

    4.  **int read():** 从此输入流中读取下一个字节的数据。值字节作为 0 到 255 范围内的 int 返回。如果因为已经到达流的末尾而没有字节可用，则返回值-1。此方法会一直阻塞，直到输入数据可用、检测到流的结尾或引发异常。

        ```
        Syntax: public int read()
        Returns: the next byte of data, or -1 if 
        the end of the stream has been reached.
        Exception: IOException - if this input stream 
        has been closed by invoking its close() method, or an I/O error occurs.

        ```

    5.  **int read(byte[] b，int off，int len):** 从这个输入流中读取多达 len 个字节的数据到一个字节数组中。此方法首先读取任何推回的字节；此后，如果读取的字节少于 len 字节，则从底层输入流中读取。如果 len 不为零，则该方法阻塞，直到至少有 1 个字节的输入可用；否则，不读取字节，返回 0。

        ```
        Syntax: public int read(byte[] b, int off, int len).
        Returns: the total number of bytes read into 
        the buffer, or -1 if there is no more data because the end of 
        the stream has been reached.
        Exception:  NullPointerException - If b is null.
        IndexOutOfBoundsException - If off is negative, len is negative, or 
        len is greater than b.length - off
        IOException - if this input stream has been closed by invoking its 
        close() method, or an I/O error occurs.

        ```

        ## 爪哇语言（一种计算机语言,尤用于创建网站)

        ```
        // Java code illustrating read() method

        import java.io.ByteArrayInputStream;
        import java.io.IOException;
        import java.io.PrintWriter;
        import java.io.PushbackInputStream;

        public class PushbackInputStreamDemo 
        {
            public static void main(String arg[]) throws IOException
            {
                PrintWriter pw = new PrintWriter(System.out, true);
                String str = "GeeksforGeeks a computer science portal ";
                byte b[] = str.getBytes();
                ByteArrayInputStream bout = new ByteArrayInputStream(b);
                PushbackInputStream push = new PushbackInputStream(bout);

                int c;
                while((c=push.read())!=-1)
                {
                    pw.print((char)c);
                }
                pw.println();
                push.read(b, 0, 13);
                for(int i=0; i<13; i++)
                {
                    pw.print((char)b[i]);
                }
                pw.println();
                pw.close();
            }
        }
        ```

        输出:

        ```
        GeeksforGeeks a computer science portal 
        GeeksforGeeks

        ```

    6.  **无效标记(int readlimit):** 标记该输入流中的当前位置。
        推回输入流的标记方法不做任何事情。

        ```
        Syntax: public void mark(int readlimit)
        Returns: NA
        Exception: NA

        ```

    7.  **void reset():** 将此流重新定位到上次在此输入流上调用 mark 方法时的位置。
        类推回输入流的方法重置除了抛出一个 IOException 之外什么都不做。

        ```
        Syntax: public void reset()
        Returns: NA
        Exception: IOException - if this method is invoked.

        ```

        ## 爪哇语言（一种计算机语言,尤用于创建网站)

        ```
        // Java code illustrating mark() and reset() method

        import java.io.ByteArrayInputStream;
        import java.io.IOException;
        import java.io.PrintWriter;
        import java.io.PushbackInputStream;

        public class PushbackInputStreamDemo 
        {
            public static void main(String arg[]) throws Exception
            {
                PrintWriter pw = new PrintWriter(System.out, true);
                String str = "GeeksforGeeks a computer science portal ";
                byte b[] = str.getBytes();
                ByteArrayInputStream bout = new ByteArrayInputStream(b);
                PushbackInputStream push = new PushbackInputStream(bout);

                int c;
                while((c=push.read())!=-1)
                {
                    pw.print((char)c);
                }
                pw.println();

                // marking the position 
                push.mark(5);

                // reseting is not supported throw exception
                push.reset();

                pw.close();
            }
        }
        ```

        输出:

        ```
        GeeksforGeeks a computer science portal 
        Exception in thread "main" java.io.IOException: mark/reset not supported
            at java.io.PushbackInputStream.reset(PushbackInputStream.java:364)
            at PushbackInputStreamDemo.main(PushbackInputStreamDemo.java:29)

        ```

    8.  **void unread(byte[] b):** 通过将字节数组复制到推回缓冲区的前面来推回字节数组。此方法返回后，下一个要读取的字节将具有值 b[0]，其后的字节将具有值 b[1]，依此类推。

        ```
        Syntax: public void unread(byte[] b)
        returns: NA
        Exception: IOException - If there is not enough room in 
        the pushback buffer for the specified number of bytes, or this input 
        stream has been closed by invoking its close() method.

        ```

    9.  **void unread(byte[] b，int off，int len):** 通过将字节数组复制到推回缓冲区的前面来推回字节数组。此方法返回后，下一个要读取的字节将具有值 b[0]，其后的字节将具有值 b[1]，依此类推。

        ```
        Syntax: public void unread(byte[] b,int off,int len)
        Returns: NA
        Exception: IOException - If there is not enough room 
        in the pushback buffer for the specified number of bytes, or this input 
        stream has been closed by invoking its close() method.

        ```

        ## 爪哇语言（一种计算机语言,尤用于创建网站)

        ```
        // Java code illustrating unread() method

        import java.io.ByteArrayInputStream;
        import java.io.IOException;
        import java.io.PrintWriter;
        import java.io.PushbackInputStream;

        public class PushbackInputStreamDemo 
        {
            public static void main(String arg[]) throws Exception
            {
                PrintWriter pw = new PrintWriter(System.out, true);
                String str = "GeeksforGeeks a computer science portal ";
                byte b[] = str.getBytes();
                ByteArrayInputStream bout = new ByteArrayInputStream(b);
                PushbackInputStream push = new PushbackInputStream(bout);

                int c;
                while((c=push.read())!=-1)
                {
                    pw.print((char)c);
                }
                pw.println();

              // unread method
                push.unread(b);
                push.unread(b, 0, 6);

                while((c=push.read())!=-1)
                {
                    pw.print((char)c);
                }
                pw.println();
                pw.close();
            }
        }
        ```

        输出:

        ```
        GeeksforGeeks a computer science portal
        orGeeks a computer science portal

        ```

    10.  **void unread(int b):** 通过将一个字节复制到推回缓冲区的前面来推回该字节。此方法返回后，下一个要读取的字节将具有值(字节)b.

        ```
        Syntax: public void unread(int b)
        Returns: NA
        Exception: IOException - If there is not enough 
        room in the pushback buffer for the byte, or this input stream 
        has been closed by invoking its close() method.

        ```

        ## Java 语言（一种计算机语言,尤用于创建网站)

        ```
        // java code illustrating unread() method

        import java.io.ByteArrayInputStream;
        import java.io.IOException;
        import java.io.PrintWriter;
        import java.io.PushbackInputStream;

        public class PushbackInputStreamDemo 
        {
            public static void main(String arg[]) throws Exception
            {
                PrintWriter pw = new PrintWriter(System.out, true);
                String str = "GeeksforGeeks a computer science portal ";
                byte b[] = str.getBytes();
                ByteArrayInputStream bout = new ByteArrayInputStream(b);
                PushbackInputStream push = new PushbackInputStream(bout);

              // unread method
                push.unread('A');
                b[1] = (byte)push.read();
                pw.println((char)b[1]);
            }
        }
        ```

        输出:

        ```
        A

        ```

    本文由**阿比舍克·维尔马**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org/)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

    如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。