# Java 中的 ByteArrayOutputStream write()方法，示例

> 原文:[https://www . geeksforgeeks . org/bytearayoputstream-write-method-in-Java-with-examples/](https://www.geeksforgeeks.org/bytearrayoutputstream-write-method-in-java-with-examples/)

Java 中 **ByteArrayOutputStream** 类的 **write()** 方法有两种使用方式:

1.Java 中 **ByteArrayOutputStream** 类的 **write(int)** 方法用于将指定的字节写入 ByteArrayOutputStream。这个指定的字节在这个 write()方法中作为整数类型参数传递。这个 write()方法一次写一个字节。

**语法:**

```java
public void write(int b)

```

**指定者:**此方法由**输出流**类的 write()方法指定。

**参数:**该方法接受一个参数 b，代表要写入的字节。

**返回值:**该方法不返回值。

**异常:**此方法不抛出任何异常。

下面的程序说明了 IO 包中 ByteArrayOutputStream 类中的 write(int)方法:

**程序:**

```java
// Java program to illustrate
// ByteArrayOutputStream write(int) method

import java.io.*;

public class GFG {
    public static void main(String[] args)
        throws Exception
    {

        // Create byteArrayOutputStream
        ByteArrayOutputStream byteArrayOutStr
            = new ByteArrayOutputStream();

        // Write byte
        // to byteArrayOutputStream

        byteArrayOutStr.write(71);

        byteArrayOutStr.write(69);

        byteArrayOutStr.write(69);

        byteArrayOutStr.write(75);

        byteArrayOutStr.write(83);

        // Print the byteArrayOutputStream
        System.out.println(
            byteArrayOutStr.toString());
    }
}
```

**Output:**

```java
GEEKS

```

2.Java 中 **ByteArrayOutputStream** 类的 **write(byte[ ]，int，int)** 方法用于从字节数组的给定偏移量开始，将给定数量的字节从给定的字节数组写入
BytearrayOutStream。此方法不同于上面的 write()方法，因为它可以一次写入几个字节。

**语法:**

```java
public void write(byte[ ] b,
                  int offset,
                  int length)

```

**覆盖:**该方法覆盖**输出流**类的 write()方法。

**参数:**该方法接受三个参数:

*   **b**–表示字节数组。
*   **偏移量**–表示字节数组中的起始索引。
*   **长度**–表示要写入的字节数。

**返回值:**该方法不返回值。

**异常:**此方法不抛出任何异常。

下面的程序举例说明了 IO 包中 ByteArrayOutputStream 类的 write(byte[ ]，int，int)方法:

**程序:**

```java
// Java program to illustrate
// ByteArrayOutputStream
// write(byte[ ], int, int) method

import java.io.*;

public class GFG {
    public static void main(String[] args)
        throws Exception
    {

        // Create byteArrayOutputStream
        ByteArrayOutputStream byteArrayOutStr
            = new ByteArrayOutputStream();

        // Create byte array
        byte[] buf = { 71, 69, 69, 75, 83,
                       70, 79, 82, 71, 69,
                       69, 75, 83 };

        // Write byte array
        // to byteArrayOutputStream
        byteArrayOutStr.write(buf, 8, 5);

        // Print the byteArrayOutputStream
        System.out.println(
            byteArrayOutStr.toString());
    }
}
```

**Output:**

```java
GEEKS

```

**参考资料:**
1。[https://docs . Oracle . com/javae/10/docs/API/Java/io/bytearray output stream . html # write(int)](https://docs.oracle.com/javase/10/docs/api/java/io/ByteArrayOutputStream.html#write(int))
2。[https://docs . Oracle . com/javae/10/docs/API/Java/io/bytearray output stream . html # write(字节%5B%5D，int，int)](https://docs.oracle.com/javase/10/docs/api/java/io/ByteArrayOutputStream.html#write(byte%5B%5D, int, int))