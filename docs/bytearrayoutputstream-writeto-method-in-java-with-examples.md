# Java 中的 ByteArrayOutputStream writeTo()方法，示例

> 原文:[https://www . geeksforgeeks . org/bytearayoputstream-write to-method-in-Java-with-examples/](https://www.geeksforgeeks.org/bytearrayoutputstream-writeto-method-in-java-with-examples/)

Java 中 **ByteArrayOutputStream** 类的 **writeTo()** 方法用于将此**BytearrayOutStream**的内容写入指定的**输出流**，该输出流作为参数传递。在此方法中，输出流作为参数传递，字节数组输出流被复制到此输出流。

**语法:**

```java
public void writeTo(OutputStream outputStr)
             throws IOException

```

**参数:**该方法接受一个参数 outputStr，该参数表示字节数组 OutputStream 的内容要复制到的输出流。

**返回值:**该方法不返回值。

**异常:**如果出现输入输出错误，该方法抛出**异常**。

下面的程序说明了 IO 包中 ByteArrayOutputStream 类中的 writeTo()方法:

**程序 1:**

```java
// Java program to illustrate
// ByteArrayOutputStream writeTo() method

import java.io.*;

public class GFG {
    public static void main(String[] args)
        throws Exception
    {

        // Create byteArrayOutputStream
        ByteArrayOutputStream byteArrayOutStr
            = new ByteArrayOutputStream();

        // Create byte array
        byte[] buf = { 71, 69, 69, 75, 83 };

        // Create outputStream
        OutputStream outputStr
            = new ByteArrayOutputStream();

        // Write byte array
        // to byteArrayOutputStream
        byteArrayOutStr.write(buf);

        // Copy byteArrayOutputStream
        // to OutputStream
        byteArrayOutStr.writeTo(outputStr);

        // Print the OutputStream
        System.out.println(
            outputStr.toString());
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
// ByteArrayOutputStream writeTo() method

import java.io.*;

public class GFG {
    public static void main(String[] args)
        throws IOException
    {

        // Create byteArrayOutputStream
        ByteArrayOutputStream byteArrayOutStr
            = new ByteArrayOutputStream();

        // Create byte array
        byte[] buf = { 71, 69, 69, 75, 83,
                       70, 79, 82, 71, 69,
                       69, 75, 83 };

        // Create outputStream
        OutputStream outputStr
            = new ByteArrayOutputStream();

        // Write byte array
        // to byteArrayOutputStream
        byteArrayOutStr.write(buf);

        // Copy byteArrayOutputStream
        // to OutputStream
        byteArrayOutStr.writeTo(outputStr);

        // Print the OutputStream
        System.out.println(
            outputStr.toString());
    }
}
```

**Output:**

```java
GEEKSFORGEEKS

```

**参考:**
[https://docs . Oracle . com/javae/10/docs/API/Java/io/bytearray output stream . html # write to(Java . io . output stream)](https://docs.oracle.com/javase/10/docs/api/java/io/ByteArrayOutputStream.html#writeTo(java.io.OutputStream))