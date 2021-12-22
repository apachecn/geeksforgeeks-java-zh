# Java.io.RandomAccessFile 类方法|集合 2

> 原文:[https://www . geesforgeks . org/Java-io-randomaccessfile-class-method-set-2/](https://www.geeksforgeeks.org/java-io-randomaccessfile-class-method-set-2/)

[Java . io . randomaccessfile 类方法的第 1 集](https://www.geeksforgeeks.org/java-io-randomaccessfile-class-method-set-1/)、[第 3 集](https://www.geeksforgeeks.org/java-io-randomaccessfile-class-method-set-3/)、
第 5 集

12.  ****readLine():****Java . io . randomaccessfile . readLine()**从这个文件读取下一行文本，从 File Pointer 开始读取，直到文件结束。

    ```
    Syntax : 
    public final String readLine()
    Parameters : 
    -----
    Return : 
    reads the next line of text from this file

    ```** 
13.  ****readUnsignedByte():****Java . io . randomaccessfile . readUnsignedByte()**从文件中读取一个无符号的 8 位数字，从当前的 File Pointer 开始读取。

    ```
    Syntax : 
    public final int readUnsignedByte()
    Parameters : 
    ------
    Return : 
    reads an unsigned 8 bit number from file

    ```** 
14.  ****readUnsignedShort():****Java . io . randomaccessfile . readUnsignedShort()**从文件中读取一个无符号的 16 位数字，从当前的 File Pointer 开始读取。

    ```
    Syntax : 
    public final int readUnsignedShort()
    Parameters : 
    -------
    Return : 
    reads an unsigned 16 bit number from file

    ```** 
15.  ****readUTF():****Java . io . randomaccessfile . readUTF()**从文件

    ```
    Syntax : 
    public final String readUTF()
    Parameters : 
    -------
    Return : 
    Unicode String

    ```

    读入一个字符串**
16.  ****seek(长位置):****Java . io . randomaccessfile . seek(长位置)**设置文件指针位置。

    ```
    Syntax : 
    public void seek(long pos)
    Parameters : 
    pos : start position from file, measured in bytes
    Return : 
    --------

    ```** 
17.  ****setleng(long len):****Java . io . randomaccessfile . setleng(long len)**stes 文件的长度。

    ```
    Syntax : 
    public void setLength(long len)
    Parameters : 
    len : desired length of the file
    Return : 
    -------

    ```** 
18.  ****跳过 n 个字节，丢弃跳过的字节

    ```
    Syntax : 
    public int skipBytes(int n)
    Parameters : 
    n : no. of bytes to be skipped
    Return : 
    no. of bytes skipped

    ```**** 
19.  ****getChannel():****Java . io . randomaccessfile . getChannel()**返回与文件关联的唯一 FileChannel 对象。

    ```
    Syntax : 
    public final FileChannel getChannel()
    Parameters : 
    ------
    Return : 
    returns unique FileChannel object

    ```** 
20.  ******Java . io . randomaccessfile . length():**返回文件的长度。

    ```
    Syntax : 
    public long length()
    Parameters : 
    ----
    Return : 
    length of the file, measured in bytes

    ```**** 
21.  ******getfile pointer():****Java . io . randomaccessfile . getfile pointer()**返回文件中当前偏移量(以字节为单位)。

    ```
    Syntax : 
    public long getFilePointer()
    Parameters : 
    ----
    Return : 
    return current offset in the file in bytes

    ```**** 
22.  ******getFD():****Java . io . randomaccessfile . getFD()**返回带有流的文件描述符对象。

    ```
    Syntax : 
    public final FileDescriptor getFD()
    Parameters : 
    -----------
    Return : 
    file descriptor object with the stream.

    ```**** 
23.  ******close() :** **java.io.RandomAccessFile.close()** closes random access file stream and releases source associated with the stream, if any.

    ```
    Syntax : 
    public void close()
    Parameters : 
    -------
    Return : 
    -------

    ```

    ```
    // Java Program illustrating use of io.RandomAccessFile class methods
    // seek(), readLine(), readUTF(), readUnsignedByte(), readUnsignedShort(),
    // setLength(), length(), skipBytes(), getFilePointer(), getChannel(),
    // getFD(), close()

    import java.io.*;
    public class NewClass
    {
        public static void main(String[] args)
        {
            try
            {
                // Creating a new RandomAccessFile - "GEEK"
                RandomAccessFile geek = new RandomAccessFile("FILE.txt", "rw");

                // Writing to file
                geek.writeUTF("Hello Geeks For Geeks");

                geek.seek(0);

                // Use of readUTF() :
                System.out.println("Use of readUTF() : " + geek.readUTF());

                //Use of seek() :
                geek.seek(0);

                // Use of readLine() :
                System.out.println("1 readLine() : " + geek.readLine());
                geek.seek(0);

                geek.writeUTF("Hello \nGeeks For Geeks");
                geek.seek(0);

                System.out.println("2 readLine() : " + geek.readLine());

                geek.seek(3);
                // Use of readUnsignedByte() :
              System.out.println("Use of readUnsignedByte() :  " + geek.readUnsignedByte());

                geek.seek(4);
                // Use of readUnsignedShort() :
              System.out.println("Use of readUnsignedByte() :  " + geek.readUnsignedShort());

                // Use of setLength():
                geek.setLength(78);

                // Use of length() :
                System.out.println("Use of setLength() : " + geek.length());

                geek.seek(2);
                // Use of skipBytes() :
                System.out.println("Use of skipBytes() : " + geek.skipBytes(3));

                // Use of getFilePointer() :
                System.out.println("Use of getFilePointer() : " + geek.getFilePointer());

                // Use of getChannel() :
                System.out.println("Use of getChannel() : " + geek.getChannel());

                // Use of getFD() :
                System.out.println("Use of getFD() : " + geek.getFD());

                // Use of close() method :
                geek.close();
                System.out.println("Stream Closed.");

            }
            catch (IOException ex)
            {
                System.out.println("Something went Wrong");
                ex.printStackTrace();
            }
        }
    }
    ```

    **输出:**

    ```
    Use of readUTF() : Hello Geeks For Geeks
    1 readLine() : Hello Geeks For Geekss
    2 readLine() : Hello
    Use of readUnsignedByte() :  101
    Use of readUnsignedByte() :  27756
    Use of setLength() : 78
    Use of skipBytes() : 3
    Use of getFilePointer() : 5
    Use of getChannel() : sun.nio.ch.FileChannelImpl@15db9742
    Use of getFD() : java.io.FileDescriptor@6d06d69c
    Stream Closed.

    ```

    本文由 <font color="green">**Mohit Gupta_OMG 供稿😀**</font> 。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

    如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。****