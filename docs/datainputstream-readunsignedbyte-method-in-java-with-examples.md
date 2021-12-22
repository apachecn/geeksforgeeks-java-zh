# Java 中的 DataInputStream readUnsignedByte()方法，带示例

> 原文:[https://www . geesforgeks . org/datainputstream-readunsignedbyte-method-in-Java-with-examples/](https://www.geeksforgeeks.org/datainputstream-readunsignedbyte-method-in-java-with-examples/)

Java 中 **DataInputStream** 类的 **readUnsignedByte()** 方法用于读取字节，并以整数形式返回。整数是 0 到 255 范围内的无符号值。此方法中的字节是从容纳的输入流中读取的。

**语法:**

```java
public final int readUnsignedByte()
                 throws IOException

```

**指定者:**此方法由**数据输入**界面的 readUnsignedByte()方法指定。

**参数:**此方法不接受任何参数。

**返回值:**该方法返回以整数形式读取的字节值。它是一个无符号的 8 位字节。

**异常:**

*   **异常**–如果输入流结束，它将抛出**异常**。
*   **IOException**–如果流关闭或发生其他输入/输出错误，该方法将抛出 **IOException** 。

下面的程序说明了 IO 包中 DataInputStream 类的 readUnsignedByte()方法:

**程序 1:**

```java
// Java program to illustrate
// DataInputStream readUnsignedByte() method
import java.io.*;
public class GFG {
    public static void main(String[] args)
        throws IOException
    {

        // Create byte array
        byte[] b = { 10, 20, 30, 40, 50 };

        // Create byte array input stream
        ByteArrayInputStream byteArrayInputStr
            = new ByteArrayInputStream(b);

        // Convert byte array input stream to
        // DataInputStream
        DataInputStream dataInputStr
            = new DataInputStream(
                byteArrayInputStr);

        while (dataInputStr.available() > 0) {
            // Print bytes
            System.out.println(
                dataInputStr.readUnsignedByte());
        }
    }
}
```

**Output:**

```java
10
20
30
40
50

```

**程序 2:**

```java
// Java program to illustrate
// DataInputStream readUnsignedByte() method
import java.io.*;
public class GFG {
    public static void main(String[] args)
        throws IOException
    {

        // Create byte array
        byte[] b = { -20, -10, 0, 10, 20 };

        // Create byte array input stream
        ByteArrayInputStream byteArrayInputStr
            = new ByteArrayInputStream(b);

        // Convert byte array input stream to
        // DataInputStream
        DataInputStream dataInputStr
            = new DataInputStream(
                byteArrayInputStr);

        while (dataInputStr.available() > 0) {
            // Print bytes
            System.out.println(
                dataInputStr.readUnsignedByte());
        }
    }
}
```

**Output:**

```java
236
246
0
10
20

```

**参考资料:**
[https://docs . Oracle . com/javae/10/docs/API/Java/io/datainputstream . html # read signed byte()](https://docs.oracle.com/javase/10/docs/api/java/io/DataInputStream.html#readUnsignedByte())