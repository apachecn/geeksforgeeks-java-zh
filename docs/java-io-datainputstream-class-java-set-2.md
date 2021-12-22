# Java 中的 Java.io.DataInputStream 类|集合 2

> 原文:[https://www . geesforgeks . org/Java-io-datainputstream-class-Java-set-2/](https://www.geeksforgeeks.org/java-io-datainputstream-class-java-set-2/)

[Java 中的 Java.io.DataInputStream 类|集合 1](https://www.geeksforgeeks.org/java-io-datainputstream-class-java-set-1/)

**更多方法:**

*   **byte readbyte ():** Reads and returns an input byte.

    ```java
    Syntax:public final byte readByte()
                        throws IOException
    Returns: the next byte of this input stream as a signed 8-bit byte.
    Throws:
    EOFException
    IOException 

    ```

*   **float read float ():** Read four input bytes and return a floating point value.

    ```java
    Syntax:public final float readFloat()
                          throws IOException
    Returns :the next four bytes of this input stream, interpreted as a float.
    Throws: EOFException 
    IOException
    ```

*   [T1】 void readFully (byte [] b): Read some bytes from the input stream and store them in buffer array B.

    ```java
    Syntax:public final void readFully(byte[] b)
                         throws IOException
    Parameters: b - the buffer into which the data is read.
    Throws: EOFException
    IOException
    ```

*   [T1】 void readFully (byte [] b, int off, int len): Read len bytes from the input stream.

    ```java
    Syntax:public final void readFully(byte[] b,
                 int off,
                 int len)
                         throws IOException
    Parameters: b - the buffer into which the data is read.
    off - the start offset of the data.
    len - the number of bytes to read.
    Throws: EOFException 
    IOException
    ```

*   **String readline ():** Read the next line of text from the input stream.

    ```java
    Syntax:
    Returns: the next line of text from this input stream.
    Throws: IOException
    *Deprecated This method does not properly convert bytes to characters.*

    ```

*   **Long readLong():** Read 8 input bytes and return a long value.

    ```java
    Syntax:public final long readLong()
                        throws IOException
    Returns: the next eight bytes of this input stream, interpreted as a long.
    Throws:
    EOFException
    IOException
    ```

*   **Short read short ():** Read two input bytes and return a short value.

    ```java
    Syntax:public final short readShort()
                          throws IOException
    Returns:
    the next two bytes of this input stream, interpreted as a signed 16-bit number.
    Throws:
    EOFException
    IOException
    ```

*   **String read UTF ():** Read the string encoded in the modified UTF-8 format.

    ```java
    Syntax:public final String readUTF()
                         throws IOException
    Returns:
    a Unicode string.
    Throws: EOFException 
    IOException
    UTFDataFormatException 

    ```

*   **int skip bytes (int n):** Try to skip n bytes of data in the input stream and discard the skipped bytes.

    ```java
    Syntax:public final int skipBytes(int n)
                        throws IOException
    Parameters: n - the number of bytes to be skipped.
    Returns: the actual number of bytes skipped.
    Throws:
    IOException
    ```

**节目 2:**

```java
//Java program to demonstrate DataInputStream
// This program uses try-with-resources. It requires JDK 7 or later.
import java.io.*;
import java.lang.reflect.Array;
import java.util.Arrays;

class DataInputStreamDemo
{
    public static void main(String args[]) throws IOException
    {
        //writing the data.
        try ( DataOutputStream dout =
                    new DataOutputStream(new FileOutputStream("file.dat")) )
        {
            dout.writeBytes("1");
            dout.writeFloat(4.4545f);
            dout.writeUTF("geeksforgeeks");
            dout.writeChars("GeeksforGeeks\n");
            dout.writeBytes("ABCDEFG");

        }

        catch(FileNotFoundException ex)
        {
            System.out.println("Cannot Open the Output File");
            return;
        }

        // reading the data back.
        try ( DataInputStream din =
                    new DataInputStream(new FileInputStream("file.dat")) )
        {

            //illustrating readByte() method
            byte t=din.readByte();

            //illustrating readFloat() method
            float u=din.readFloat();

            //illustrating readUTF() method
            String temp=din.readUTF();

            //illustrating readLine() method
            String temp1=din.readLine();

            System.out.println("Values: " + t +" "+" "+u+" "+temp+" "+temp1 );

            //illustrating skipBytes() method
            //skipping "AB"
            din.skipBytes(2);

            //illustrating readFully() method
            byte[] b=new byte[4];
            din.readFully(b,0,4);
            System.out.println(Arrays.toString(b));

        }
        catch(FileNotFoundException e)
        {
            System.out.println("Cannot Open the Input File");
            return;
        }
    }
}
```

**输出:**

```java
Values: 49  4.4545 geeksforgeeks  GeeksforGeeks 
[67, 68, 69, 70]
```

本文由 **[尼尚·夏尔马](https://www.facebook.com/ChippingEye2766)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。