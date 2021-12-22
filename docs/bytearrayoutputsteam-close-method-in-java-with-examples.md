# Java 中的 ByteArrayOutputSteam close()方法，示例

> 原文:[https://www . geeksforgeeks . org/bytearayooutsteam-close-method-in-Java-with-examples/](https://www.geeksforgeeks.org/bytearrayoutputsteam-close-method-in-java-with-examples/)

Java 中 **ByteArrayOutputStream** 类的 **close()** 方法，如果在关闭 BytearrayOutStream 后调用该类的其他方法，则没有效果。即使在关闭字节数组输出流后，调用另一个方法，该方法也不会引发异常。

**语法:**

```java
public void close()

```

**指定者:**此方法由**可自动关闭**界面的关闭()方法和**可关闭**界面的关闭()方法指定。

**覆盖:**该方法覆盖**输出流**类的 close()方法。

**参数:**此方法不接受任何参数。

**返回值:**此方法不返回值。

**异常:**此方法不抛出任何异常。

下面的程序说明了 IO 包中 ByteArrayOutputStream 类中的 close()方法:

**程序 1:**

```java
// Java program to illustrate
// ByteArrayOutputStream close() method

import java.io.*;

public class GFG {
    public static void main(String[] args)
 throws IOException
    {
        try {

            // Create byteArrayOutputStream
            ByteArrayOutputStream byteArrayOutStr
                = new ByteArrayOutputStream();

            // Create byte array
            byte[] buf = { 71, 69, 69, 75, 83 };

            // close() is called
            byteArrayOutStr.close();

            // Write byte array
            // to byteArrayOutputStream
            byteArrayOutStr.write(buf);

            // Print the byteArrayOutputStream
            // as String
            System.out.println(
                byteArrayOutStr.toString());
        }
        catch (Exception e) {
            System.out.println(
                "ByteArrayOutputStream is closed");
        }
    }
}
```

**Output:**

```java
GEEKS

```

**程序 2:**

```java
// Java program to illustrate
// ByteArrayOutputStream close() method

import java.io.*;

public class GFG {
    public static void main(String[] args)
 throws IOException
    {
        try {

            // Create byteArrayOutputStream
            ByteArrayOutputStream byteArrayOutStr
                = new ByteArrayOutputStream();

            // Create byte array
            byte[] buf1 = { 71, 69, 69, 75, 83 };
            byte[] buf2 = { 70, 79, 82 };

            // Write byte array
            // to byteArrayOutputStream
            byteArrayOutStr.write(buf1);

            // close() is called
            byteArrayOutStr.close();

            // Write byte array
            // to byteArrayOutputStream
            byteArrayOutStr.write(buf2);

            // close() is called again
            byteArrayOutStr.close();

            // Write byte array
            // to byteArrayOutputStream
            byteArrayOutStr.write(buf1);

            // Print the byteArrayOutputStream
            // as String
            System.out.println(
                byteArrayOutStr.toString());
        }
        catch (Exception e) {
            System.out.println(
                "ByteArrayOutputStream is closed");
        }
    }
}
```

**Output:**

```java
GEEKSFORGEEKS

```

**参考文献:**
[https://docs . Oracle . com/javase/10/docs/API/Java/io/bytearrayouttstream . html # close()](https://docs.oracle.com/javase/10/docs/api/java/io/ByteArrayOutputStream.html#close())