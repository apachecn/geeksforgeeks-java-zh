# Java.io.RandomAccessFile 类方法|集合 3

> 原文:[https://www . geesforgeks . org/Java-io-randomaccessfile-class-method-set-3/](https://www.geeksforgeeks.org/java-io-randomaccessfile-class-method-set-3/)

[第一套](https://www.geeksforgeeks.org/java-io-randomaccessfile-class-method-set-1/)、[第二套](https://www.geeksforgeeks.org/java-io-randomaccessfile-class-method-set-2/)

**io 的更多方法。RandomAccessFile 类:**

25.  **write(int 字节):****Java . io . randomaccessfile . write(int 字节)**从当前文件指针开始向文件写入指定字节。

    ```java
    Syntax : 
    public void write(int bytes)
    Parameters :
    bytes : bytes to be written 
    Return :
    -----
    Exception :
    IOException :in case an I/O error occurs.

    ```

26.  **写入(字节[]b):****Java . io . randomaccessfile . write(字节[] b)** 从当前文件指针开始，将特定字节数组中的 b.length 字节写入文件。

    ```java
    Syntax : 
    public void write(byte[] b)
    Parameters :
    b : data to be written
    Return :
    -------
    Exception :
    IOException :in case an I/O error occurs.

    ```

27.  **写入(字节[] b，int offset，int len):****Java . io . randomaccessfile . write(字节[] b，int offset，int len)** 写入从偏移量位置到缓冲区 b . len 长度的初始化字节。

    ```java
    Syntax : 
    public int write(byte[] b, int offset, int len)
    Parameters :
    b : buffer to write
    offset : starting position to write
    len : max no of bytes to write
    Return :
    ---------
    Exception :
    IOException :in case an I/O error occurs.

    ```

28.  **写布尔(布尔 b):****Java . io . randomaccessfile . write 布尔(布尔 b)** 将布尔作为一字节值写入文件。真被写为值为‘1’否则为假

    ```java
    Syntax : 
    public final void writeBoolean(boolean b)
    Parameters :
    b : boolean value to be written 
    Return :
    ---------
    Exception :
    IOException :in case an I/O error occurs.

    ```

29.  **书写字节(int b):****Java . io . random MAC file . write byte(int b)**

    ```java
    writes a byte to file as one-byte value, starting from the current position.
    Syntax : 
    public final void writeByte(int b)
    Parameters :
    b : byte to be written 
    Return :
    ---------
    Exception :
    IOException :in case an I/O error occurs.

    ```

30.  **write Short(int b):****Java . io . randomaccessfile . write short(int b)**从当前位置开始，以双字节值的形式向文件写入一个 short。

    ```java
    Syntax : 
    public final void writeShort(int b)
    Parameters :
    b : short to be written
    Return :
    ---------
    Exception :
    IOException :in case an I/O error occurs.

    ```

31.  **write char(int c):****Java . io . randomaccessfile . write char(int c)**从当前位置开始，将一个字符作为两字节值写入文件。

    ```java
    Syntax : 
    public final void writeChar(int c)
    Parameters :
    c : char to be written 
    Return :
    ---------
    Exception :
    IOException :in case an I/O error occurs.

    ```

32.  **writeInt(Int I):****Java . io . randomaccessfile . writeInt(int I)**从当前位置开始，将一个 int 作为四字节值写入文件。

    ```java
    Syntax : 
    public final void writeInt(int i)
    Parameters :
    i : int value to be written
    Return :
    ---------
    Exception :
    IOException :in case an I/O error occurs.

    ```

33.  **write long(long l):****Java . io . randomaccessfile . write long(long l)**从当前位置开始，将一个 int 作为八字节值写入文件。

    ```java
    Syntax : 
    public final void writeLong(long l)
    Parameters :
    l : long value to be written
    Return :
    ---------
    Exception :
    IOException :in case an I/O error occurs.

    ```

34.  **write Float(float f):****Java . io . randomaccessfile . write float(float f)**将 float 参数转换为 int，然后将一个 int 作为四字节值写入文件，从当前位置开始。

    ```java
    Syntax : 
    public final void writeFloat(float f)
    Parameters :
    f : float value to be written
    Return :
    ---------
    Exception :
    IOException :in case an I/O error occurs.

    ```

35.  **write Double(double d):****Java . io . randomaccessfile . write double(double d)** 将 double 参数转换为 long，然后将一个 int 作为 8 字节值写入文件，从当前位置开始。

```java
Syntax : 
public final void writeDouble(double d)
Parameters :
d : double value to be written
Return :
---------
Exception :
IOException :in case an I/O error occurs.

```

*   **写字节(字符串):****Java . io . randomaccessfile . writeBytes(字符串)**将字符串作为字节序列写入文件。

    ```java
    Syntax : 
    public final void writeBytes(String s)
    Parameters :
    s : byte string to be written
    Return :
    ---------
    Exception :
    IOException :in case an I/O error occurs.

    ```

    *   **writeUTF(String str) :** **java.io.RandomAccessFile.writeUTF(String str)** writes a string to file using modified **UTF-8** encoding(machine-independent)

    ```java
    Syntax : 
    public final void writeUTF(String str)
    Parameters :
    str : String to be written 
    Return :
    ---------
    Exception :
    IOException :in case an I/O error occurs.

    ```

    ```java
    // Java Program illustrating use of io.RandomAccessFile class methods
    // writeUTF(), writeChar(), writeDouble(), writeFloat(), write(byte[] b), 
    // write(int i), writeBoolean(), writeLong(), writeShort()
    // write(byte[] b, int offset, int len)

    import java.io.*;
    public class NewClass
    {
        public static void main(String[] args)
        {
            try
            {
                long l = 458754545576l;
                double d = 1.5;
                float f = 14.56f;
                int i = 1;
                boolean bol = true;
                short s = 15; 

                // Creating a new RandomAccessFile - "GEEK"
                RandomAccessFile geek = new RandomAccessFile("GEEK.txt", "rw");

                // writeUTF() : 
                geek.writeUTF("Hello Geeks For Geeks");

                geek.seek(0);
                System.out.println("writeUTF : " + geek.readUTF()); 
                geek.seek(0);

                byte[] b = {1, 2, 3, 6, 5, 4};

                // write(byte[] b) : 
                geek.write(b);

                geek.seek(0);
                System.out.println("Use of .read(byte[] b) : " + geek.read(b));

                // write(int i) :  
                geek.write(i);

                geek.seek(0);
                System.out.println("write(int i) : " + geek.read(b));

                // writeBoolean() : 
                geek.writeBoolean(bol);            

                geek.seek(0);
                System.out.println("writeBoolean() : " + geek.readBoolean());

                geek.write(b, 2, 2);
                geek.seek(0);
          System.out.println("write(byte[] b, int offset, int len) : " + geek.readByte());

                // writeChar() : 
                geek.writeChar('c');

                geek.seek(0);
                System.out.println("writeChar() : " + geek.readChar()); 
                geek.seek(0);

                // writeDouble() : 
                geek.writeDouble(d);

                geek.seek(0);            
                System.out.println("writeDouble() : " + geek.readDouble()); 
                geek.seek(0);

                //writeFloat() : 
                geek.writeFloat(f);

                geek.seek(0);
                System.out.println("writeFloat() : " + geek.readFloat()); 

                // writeLong() :
                geek.writeLong(l);

                geek.seek(0);
                System.out.println("writeLong() : " + geek.readLong()); 

                // writeShort() :
                geek.writeShort(s);

                geek.seek(0);
                System.out.println("writeShort() : " + geek.readShort());  

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

    ```java
    writeUTF : Hello Geeks For Geeks
    Use of .read(byte[] b) : 6
    write(int i) : 6
    writeBoolean() : true
    write(byte[] b, int offset, int len) : 1
    writeChar() : c
    writeDouble() : 1.5
    writeFloat() : 14.56
    writeLong() : 4713287227910652010
    writeShort() : 16744

    ```

    本文由 <font color="green">**Mohit Gupta_OMG 供稿😀**</font> 。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

    如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。