# 使用文件输出流创建文件

> 原文:[https://www . geesforgeks . org/creating-a-file-using-file outputstream/](https://www.geeksforgeeks.org/creating-a-file-using-fileoutputstream/)

FileOutputStream 类属于字节流，以单个字节的形式存储数据。它可以用来创建文本文件。文件表示数据在第二存储介质(如硬盘或光盘)上的存储。文件是否可用或是否可以创建取决于底层平台。尤其是一些平台，一次只允许一个文件输出流(或其他文件写入对象)打开文件进行写入。在这种情况下，如果涉及的文件已经打开，这个类中的构造函数将失败。

FileOutputStream 用于写入原始字节流，如图像数据。要编写字符流，请考虑使用文件编写器。

**重要方法:**

*   **void close ():** Close this fileoutputstream and release any system resources associated with this stream.
*   **Protected void finalize ():** Clean up the connection with the file and make sure to call the close method of this fileoutputstream when there are no more references to this stream.
*   **Invalid write (byte [] b):** Write the b.length byte in the specified byte array into this fileoutputstream.
*   **Voidwrite (byte [] b, int off, int len):** Write len bytes in the specified byte array starting from offset off into this fileoutputstream.
*   **Voidwrite (int b):** Write the specified byte into this fileoutputstream.

**按照以下步骤创建一个存储一些字符(或文本)的文本文件:**

1.  **Reading data:** First of all, data should be read from the keyboard. For this purpose, associate the keyboard to some input stream class. The code for using DataInputSream class for reading data from the keyboard is as:

    ```
    DataInputStream dis =new DataInputStream(System.in);
    ```

    这里 System.in 表示与 DataInputStream 对象

2.  The linked keyboard **sends data to the output stream:** Now, associate a file to store data with an output stream. To do this, please use a fileoutputstream that can send data to files. Attaching file.txt to the FileOutputStream can be done as follows:

    ```
    FileOutputStream fout=new FileOutputStream(“file.txt”);
    ```

3.  **Reading data from DataInputStream:** The next step is to read data from DataInputStream and write it into FileOutputStream. It means reading data from dis object and writing it into fout object, as shown below:

    ```
    ch=(char)dis.read();
    fout.write(ch);
    ```

4.  **Close the file:** Finally, any file should be closed after performing input or output operations on it, otherwise the data may be destroyed. Closing a file is done by closing the related stream. For example, fout.close (): The fileoutputstream will be closed, so data cannot be written to the file.

**执行:**T0】

如果再次执行程序，file.txt 的旧数据将会丢失，任何最近的数据都只存储在文件中。如果我们不想丢失文件的先前数据，而只是将新数据追加到已经存在的数据的末尾，这可以通过在文件名的同时写入 true 来实现。

```
FileOutputStream fout=new FileOutputStream(“file.txt”,true);

```

**使用缓冲输出流提高效率**

通常，每当我们使用文件输出流将数据写入文件时，如下所示:

```
fout.write(ch);
```

这里，调用文件输出流将字符写入文件。让我们估算一下从键盘上读取 100 个字符并将它们全部写入一个文件所需的时间。

*   Let's assume that using DataInputStream to read data from keyboard into memory, it takes 1 second to read a character into memory, and it takes another 1 second for this character to be written into file by FileOutputStream.
*   So it takes 200 seconds to read and write a file. This is a waste of time. On the other hand, if buffer classes are used, they will provide a buffer, which is first filled with characters in the buffer, and these characters can be written into the file immediately. Buffer classes should be used in combination with other stream classes.
*   首先，DataInputStream 从键盘读取数据，每个字符花费 1 秒。这个字符被写入缓冲区。因此，将 100 个字符读入缓冲区需要 100 秒的时间。现在，文件输出流将在一个步骤中写入整个缓冲区。因此，读写 100 个字符只需要 101 秒。同样，阅读课也被用来提高阅读操作的速度。将文件输出流附加到缓冲区输出流为:

    ```
    BufferedOutputStream bout=new BufferedOutputStream(fout,1024);
    ```

    这里，缓冲区大小声明为 1024 字节。如果未指定缓冲区大小，则使用默认大小 512 字节

**bufferedoutstream 类的重要方法:**

*   **Voidflush ():** Refresh this buffered output stream.
*   **Voidwrite (byte [] b, int off, int len):** Write len bytes in the specified byte array starting from offset off into the buffered output stream.
*   **Voidwrite (int b):** Write the specified byte into the buffered output stream.

**输出:**

```
C:\> javac Create_File.java
C:\> java Create_File
Enter text (@ at the end):
This is a program to create a file
@

C:/> type file.txt
This is a program to create a file

```

**相关文章:**

*   [character stream vs byte stream](https://www.geeksforgeeks.org/character-stream-vs-byte-stream-java/)
*   [File class](https://www.geeksforgeeks.org/file-class-in-java/) in Java
*   [File processing in Java using FileWriter and FileReader](https://www.geeksforgeeks.org/file-handling-java-using-filewriter-filereader/)

本文由 **[尼尚·夏尔马](https://www.facebook.com/ChippingEye2766)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。