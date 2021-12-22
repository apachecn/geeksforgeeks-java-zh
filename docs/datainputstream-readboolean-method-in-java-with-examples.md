# Java 中的 DataInputStream readBoolean()方法，带示例

> 原文:[https://www . geesforgeks . org/datainputstream-readboolean-in-Java-method-with-examples/](https://www.geeksforgeeks.org/datainputstream-readboolean-method-in-java-with-examples/)

Java 中 **DataInputStream** 类的 **readBoolean()** 方法用于读取一个输入字节，如果读取的字节为零，则该方法返回 false，如果读取的字节非零，则该方法返回 true。

**语法:**

```
public final boolean readBoolean()
                throws IOException

```

**指定者:**该方法由**数据输入**界面的 readBoolean()方法指定。

**参数:**此方法不接受任何参数。

**返回值:**该方法返回读取的布尔值，即真或假。

**异常:**

*   **异常**–如果输入流结束，它将抛出**异常**。
*   **IOException**–如果流关闭或发生其他输入/输出错误，该方法将抛出 **IOException** 。

下面的程序说明了 IO 包中 DataInputStream 类的 readBoolean()方法:

**程序 1:**

```
// Java program to illustrate
// DataInputStream readBoolean() method
import java.io.*;
public class GFG {
    public static void main(String[] args)
        throws IOException
    {

        // Create byte array
        byte[] b = { 10, 0, 0, 20, 0 };

        // Create byte array input stream
        ByteArrayInputStream byteArrayInputStr
            = new ByteArrayInputStream(b);

        // Convert byte array input stream to
        // DataInputStream
        DataInputStream dataInputStr
            = new DataInputStream(
                byteArrayInputStr);

        while (dataInputStr.available() > 0) {
            // Print boolean value
            System.out.println(
                dataInputStr.readBoolean());
        }
    }
}
```

**Output:**

```
true
false
false
true
false

```

**程序 2:**

```
// Java program to illustrate
// DataInputStream readBoolean() method
import java.io.*;
public class GFG {
    public static void main(String[] args)
        throws IOException
    {

        // Create byte array
        byte[] b = { 10, 5, 7, 1, 0 };

        // Create byte array input stream
        ByteArrayInputStream byteArrayInputStr
            = new ByteArrayInputStream(b);

        // Convert byte array input stream to
        // DataInputStream
        DataInputStream dataInputStr
            = new DataInputStream(
                byteArrayInputStr);

        while (dataInputStr.available() > 0) {
            // Print boolean value
            System.out.println(
                dataInputStr.readBoolean());
        }
    }
}
```

**Output:**

```
true
true
true
true
false

```

**参考文献:**
[https://docs . Oracle . com/javase/10/docs/API/Java/io/datainputstream . html # readBoolean()](https://docs.oracle.com/javase/10/docs/api/java/io/DataInputStream.html#readBoolean())