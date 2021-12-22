# 压缩和解压缩 Java 中的文件

> 原文:[https://www . geesforgeks . org/压缩和解压缩 java 文件/](https://www.geeksforgeeks.org/compressing-and-decompressing-files-in-java/)

Java 中提供了通缩输出流和通胀输出流类来压缩和解压缩文件内容。这些类提供了可用于压缩文件内容的有用方法。

**使用压缩输出流压缩文件**

这个类实现了一个输出流过滤器，用于以“deflate”压缩格式压缩数据。它还被用作其他类型的压缩过滤器的基础，例如 GZIPOutputStream。

**重要方法:**

*   **void close() :** 将剩余的压缩数据写入输出流，并关闭底层流。
*   **受保护的 void deflate() :** 将下一个压缩数据块写入输出流。
*   **void finish() :** 完成向输出流写入压缩数据，而不关闭底层流。
*   **void flush() :** 刷新压缩的输出流。
*   **void write(byte[] b，int off，int len) :** 将字节数组写入压缩输出流，其中 off 是数据的起始偏移量，len 是字节总数。
*   **无效写入(int b) :** 向压缩的输出流写入一个字节。

**压缩文件的步骤(文件 1)**

*   Take an input file' File1' to FileInputStream for data reading.
*   Take the output file' File 2' and assign it to FileOutputStream. This will help to write data to File 2.
*   Fileoutputstream is assigned to the compressed output stream to compress data.
*   Now, read the data from the file input stream and write it into the flat output stream. It will compress the data and send it to fileoutputstream, and fileoutputstream will store the compressed data in the output file.

```
import java.io.FileInputStream;
import java.io.FileNotFoundException;
import java.io.FileOutputStream;
import java.io.IOException;
import java.util.zip.Deflater;
import java.util.zip.DeflaterOutputStream;

class zip
{
    public static void main(String[] args) throws IOException {
        //Assign the original file : file to
        //FileInputStream for reading data
        FileInputStream fis=new FileInputStream("file1");

        //Assign compressed file:file2 to FileOutputStream
        FileOutputStream fos=new FileOutputStream("file2");

        //Assign FileOutputStream to DeflaterOutputStream
        DeflaterOutputStream dos=new DeflaterOutputStream(fos);

        //read data from FileInputStream and write it into DeflaterOutputStream
        int data;
        while ((data=fis.read())!=-1)
        {
            dos.write(data);
        }

        //close the file
        fis.close();
        dos.close();
    }
}
```

**使用通货膨胀计算机流**解压缩文件

这个类实现了一个流过滤器，用于以“deflate”压缩格式解压缩数据。它还被用作其他解压缩过滤器的基础，如 GZIPInputStream。

**重要方法:**

*   **int available ():** Return 0 after reaching EOF, otherwise always return 1.
*   **void close ():** Close the input stream and release any system resources associated with the stream.
*   **Protected blank padding ():** Fill the input buffer with more data for decompression.
*   **void mark (int read limit):** Mark the current position in the input stream.
*   **Boolean flag support ():** Test whether the input stream supports the flag and reset method.
*   **int read ():** Read one byte of uncompressed data.
*   [T0】 int read(byte【】b [】 b, int off, int len): Read the decompressed data into the byte array of the compressed output stream, where off is the initial offset of the data and len is the total number of bytes.
*   **Voidreset ():** Reposition this stream to the position where the mark method was last called on this input stream.

**解压文件的步骤**

*   The file named' File 2' now contains compressed data, and we need to get the original decompressed data from this file.
*   The compressed file' File2' is assigned to the file input stream. This helps to read data from File 2.
*   Assign the output file' File 3' to fileoutputstream. This will help to write uncompressed data to File 3.
*   Now, read the uncompressed data from the inflation computer stream and write it into the fileoutputstream. This will write uncompressed data to File 3.

```
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.IOException;
import java.util.zip.InflaterInputStream;

//Uncompressing a file using an InflaterInputStream
class unzip
{
    public static void main(String[] args) throws IOException {
        //assign Input File : file2 to FileInputStream for reading data
        FileInputStream fis=new FileInputStream("file2");

        //assign output file: file3 to FileOutputStream for reading the data
        FileOutputStream fos=new FileOutputStream("file3");

        //assign inflaterInputStream to FileInputStream for uncompressing the data
        InflaterInputStream iis=new InflaterInputStream(fis);

        //read data from inflaterInputStream and write it into FileOutputStream 
        int data;
        while((data=iis.read())!=-1)
        {
            fos.write(data);
        }

        //close the files
        fos.close();
        iis.close();

    }
}
```

本文由[尼尚夏尔马](https://www.facebook.com/ChippingEye2766)供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。