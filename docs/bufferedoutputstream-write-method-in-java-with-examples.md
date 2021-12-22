# Java 中的 BufferedOutputStream write()方法，示例

> 原文:[https://www . geeksforgeeks . org/bufferedoutstream-write-method-in-Java-with-examples/](https://www.geeksforgeeks.org/bufferedoutputstream-write-method-in-java-with-examples/)

1.  The **write(int)** method of **BufferedOutputStream** class in Java is used to write the specified byte to the buffered output stream. The specified byte is passed as an integer to the write() method here. It is used to write one byte as a time to the **BufferedOutputStream**.

    **语法:**

    ```
    public void write(int b)
                throws IOException

    ```

    **覆盖:**该方法覆盖 **FilterOutputStream** 类的 **write(int)** 方法。

    **参数:**该方法接受整数类型的 **b** 作为代表要写入的字节的参数。

    **返回值:**此方法不返回值。

    **异常:**如果出现输入输出错误，该方法抛出**异常**。

    下面的程序说明了 IO 包中 BufferedOutputStream 类的 write(int)方法:

    **程序:**

    ```
    // Java program to illustrate
    // BufferedOutputStream write(int) method
    import java.io.*;
    public class GFG {
        public static void main(
            String[] args) throws Exception
        {

            // Create byteArrayOutputStream
            ByteArrayOutputStream byteArrayOutStr
                = new ByteArrayOutputStream();

            // Convert byteArrayOutputStream to
            // bufferedOutputStream
            BufferedOutputStream buffOutputStr
                = new BufferedOutputStream(
                    byteArrayOutStr);

            for (int i = 65; i < 70; i++) {
                // Writes to buffOutputStr
                buffOutputStr.write(i);
            }

            // flush is called
            // to compel bytes to be
            // written out to buffOutputStr
            buffOutputStr.flush();

            for (
                byte by : byteArrayOutStr.toByteArray()) {
                // Converts byte to character
                char ch = (char)by;
                System.out.print(ch);
            }
        }
    }
    ```

    **Output:**

    ```
    ABCDE

    ```

2.  The **write(byte[ ], int, int)** method of **BufferedOutputStream** class in Java is used to write given length of bytes from the specified byte array starting at given offset to the buffered output stream.
    Basically the write() method stores bytes from the given byte array into the buffer of a stream and flushes the buffer to the main output stream. If the length is equal to the buffer of the stream then write() method flushes the buffer and writes the bytes directly to the main output stream.

    **语法:**

    ```
    public void write(byte[] b,
                      int offset,
                      int length)
                throws IOException

    ```

    **覆盖:**该方法覆盖 **FilterOutputStream** 类中的 **write(byte[ ]，int，int)** 方法。

    **参数:**该方法接受三个参数:

    *   **b**–它是字节类型，代表字节数组。
    *   **偏移量**–整数类型，表示字节数组中的起始偏移量。
    *   **长度**–它是整数类型，代表要写入的字节数。

    **返回值:**此方法不返回值。

    **异常:**如果出现输入输出错误，该方法抛出**异常**。

    下面的程序说明了 IO 包中 BufferedOutputStream 类的 write(byte[ ]，int，int)方法:

    **程序:**

    ```
    // Java program to illustrate
    // BufferedOutputStream write(
    // byte[ ], int, int) method
    import java.io.*;
    public class GFG {
        public static void main(
            String[] args) throws Exception
        {

            // Create byteArrayOutputStream
            ByteArrayOutputStream byteArrayOutStr
                = new ByteArrayOutputStream();

            // Convert byteArrayOutputStream to
            // bufferedOutputStream
            BufferedOutputStream buffOutputStr
                = new BufferedOutputStream(
                    byteArrayOutStr);

            // Create byte array
            byte b[] = { 71, 69, 69, 75, 83 };

            // Call write(byte[ ], int, int)
            // method
            // It writes byte array to
            // buffOutputStr
            buffOutputStr.write(b, 0, 5);

            // flush is called
            // to compel bytes to be
            // written out to buffOutputStr
            buffOutputStr.flush();

            for (
                byte by : byteArrayOutStr.toByteArray()) {
                // Converts byte to character
                char ch = (char)by;
                System.out.print(ch);
            }
        }
    }
    ```

    **Output:**

    ```
    GEEKS

    ```

**参考文献:**

*   [https://docs . Oracle . com/javase/10/docs/API/Java/io/bufferedoutputstream . html # write(int)](https://docs.oracle.com/javase/10/docs/api/java/io/BufferedOutputStream.html#write(int))
*   [https://docs . Oracle . com/javae/10/docs/API/Java/io/buffer utputstream . html # write(字节%5B%5D，int，int)](https://docs.oracle.com/javase/10/docs/api/java/io/BufferedOutputStream.html#write(byte%5B%5D, int, int))