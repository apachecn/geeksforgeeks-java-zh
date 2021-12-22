# Java 中的 ByteArrayInputStream read()方法，示例

> 原文:[https://www . geeksforgeeks . org/bytearrainputstream-read-method-in-Java-with-examples/](https://www.geeksforgeeks.org/bytearrayinputstream-read-method-in-java-with-examples/)

Java 中**Bytearrainputstream**类的 **read()** 方法有两种使用方式:

1.Java 中**Bytearrainputstream**类的 **read()** 方法用于读取 Bytearrainputstream 的下一个字节。这个 read()方法返回以整数形式读取的字节，如果输入流结束，这个方法返回-1。此方法一次从流中读取一个字节。

**语法:**

```java
public int read()

```

**指定者:**该方法由 **InputStream** 类的 read()方法指定。

**参数:**此方法不接受任何参数。

**返回值:**该方法以整数形式返回读取的字节。如果流结束，则返回-1。

**异常:**此方法不抛出任何异常。

下面的程序说明了 IO 包中 ByteArrayInputStream 类中的 read()方法:

**程序:**

```java
// Java program to illustrate
// ByteArrayInputStream read() method

import java.io.*;

public class GFG {
    public static void main(String[] args)
        throws Exception
    {

        // Create byte array
        byte[] buf = { 71, 69, 69, 75, 83 };

        // Create byteArrayInputStream
        ByteArrayInputStream byteArrayInputStr
            = new ByteArrayInputStream(buf);

        int b = 0;
        while ((b = byteArrayInputStr.read()) != -1) {
            // Convert byte to character
            char ch = (char)b;

            // Print the character
            System.out.println("Char : " + ch);
        }
    }
}
```

**Output:**

```java
Char : G
Char : E
Char : E
Char : K
Char : S

```

2.Java 中**ByteArrayInputStream**类的 **read(byte[ ]，int，int)** 方法用于从 Bytearrainputstream 中读取给定数量的字节到给定的字节数组中。此方法不同于上面的 read()方法，因为它可以一次读取几个字节。它返回读取的总字节数作为返回值。

**语法:**

```java
public void read(byte[ ] b,
                 int offset,
                 int length)

```

**覆盖:**该方法覆盖 **InputStream** 类的 read()方法。

**参数:**该方法接受三个参数:

*   **b**–表示读取数据的字节数组。
*   **偏移量**–表示字节数组 b 中的起始索引。
*   **长度**–表示要读取的字节数。

**返回值:**这个方法返回读入缓冲区的字节总数。如果输入流结束，此方法返回-1。

**异常:**

*   **NullPointerException**–如果字节数组 b 为空，则该方法抛出 NullPointerException。
*   **IndexOutOfBoundsException**–如果偏移量或偏移量为负或长度为负后，长度大于输入流的长度，则此方法抛出 indexout of boundsexception。

下面的程序说明了 IO 包中 ByteArrayInputStream 类的 read(byte[ ]，int，int)方法:

**程序:**

```java
// Java program to illustrate
// ByteArrayInputStream
// read(byte[ ], int, int) method

import java.io.*;

public class GFG {
    public static void main(String[] args)
        throws Exception
    {

        // Create byte array
        byte[] buf = { 71, 69, 69, 75, 83 };

        // Create byteArrayInputStream
        ByteArrayInputStream byteArrayInputStr
            = new ByteArrayInputStream(buf);

        // Create buffer
        byte[] b = new byte[4];

        int total_bytes
            = byteArrayInputStr.read(b, 1, 3);

        // Total number of bytes read
        System.out.println("Total bytes read: "
                           + total_bytes);

        for (byte ch : b) {

            // Print the character
            if (ch == 0)
                System.out.println("NULL");

            else
                System.out.println((char)ch);
        }
    }
}
```

**Output:**

```java
Total bytes read: 3
NULL
G
E
E

```

**参考资料:**
1。[https://docs . Oracle . com/javae/10/docs/API/Java/io/bytearrayinputstream . html # read()](https://docs.oracle.com/javase/10/docs/api/java/io/ByteArrayInputStream.html#read())T2。[https://docs . Oracle . com/javae/10/docs/API/Java/io/bytearrayinputstream . html # read(字节%5B%5D，int，int)](https://docs.oracle.com/javase/10/docs/api/java/io/ByteArrayInputStream.html#read(byte%5B%5D, int, int))