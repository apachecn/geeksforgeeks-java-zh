# Java 中的 BufferedOutputStream flush()方法，示例

> 原文:[https://www . geeksforgeeks . org/bufferedoutstream-flush-in-Java-method-with-examples/](https://www.geeksforgeeks.org/bufferedoutputstream-flush-method-in-java-with-examples/)

Java 中**bufferedoutstream**类的 **flush()** 方法用于刷新缓冲的输出流。此方法用于强制将缓冲输出的字节写入主输出流。

**语法:**

```
public void flush() 
            throws IOException

```

**指定者:**该方法由**可冲洗**界面的**冲洗()**方法指定。

**覆盖:**该方法覆盖 **FilterOutputStream** 类中的 **flush()** 方法。

**参数:**此方法不接受任何参数。

**返回值:**此方法不返回值。

**异常:**如果出现输入输出错误，该方法抛出**异常**。

下面的程序说明了 IO 包中 BufferedOutputStream 类中的 flush()方法:

**程序 1:**

```
// Java program to illustrate
// BufferedOutputStream flush() method
import java.io.*;
public class GFG {
    public static void main(String[] args) throws Exception
    {

        // Create byteArrayOutputStream
        ByteArrayOutputStream
            byteArrayOutStr
            = new ByteArrayOutputStream();

        // Convert outputStream to
        // bufferedInputStream
        BufferedOutputStream buffOutputStr
            = new BufferedOutputStream(
                byteArrayOutStr);

        // Creating byte array
        byte b[] = { 71, 69, 69, 75, 83 };
        buffOutputStr.write(b);

        // flush is called
        // to compel bytes to be
        // written out to buffOutputStr
        buffOutputStr.flush();

        for (byte by : byteArrayOutStr
                           .toByteArray()) {

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

**程序 2:**

```
// Java program to illustrate
// BufferedOutputStream flush() method
import java.io.*;
public class GFG {
    public static void main(String[] args) throws Exception
    {

        // Create byteArrayOutputStream
        ByteArrayOutputStream byteArrayOutStr = new ByteArrayOutputStream();

        // Convert outputStream to
        // bufferedInputStream
        BufferedOutputStream buffOutputStr
            = new BufferedOutputStream(
                byteArrayOutStr);

        // Creating first byte array
        byte b1[] = { 71, 69, 69, 75, 83 };
        buffOutputStr.write(b1);

        // flush is called
        // to compel bytes to be
        // written out to buffOutputStr
        buffOutputStr.flush();

        // Creating second byte array
        byte b2[] = { 70, 79, 82 };
        buffOutputStr.write(b2);

        buffOutputStr.flush();

        buffOutputStr.write(b1);

        buffOutputStr.flush();

        for (byte by : byteArrayOutStr.toByteArray()) {
            // Converts byte to character
            char ch = (char)by;
            System.out.print(ch);
        }
    }
}
```

**Output:**

```
GEEKSFORGEEKS

```

**参考文献:**
[https://docs . Oracle . com/javase/10/docs/API/Java/io/bufferedoutputstream . html # flush()](https://docs.oracle.com/javase/10/docs/api/java/io/BufferedOutputStream.html#flush())