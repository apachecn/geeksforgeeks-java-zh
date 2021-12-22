# Java 中的 ByteArrayOutputStream size()方法，示例

> 原文:[https://www . geeksforgeeks . org/bytearayooutstream-size-method-in-Java-with-examples/](https://www.geeksforgeeks.org/bytearrayoutputstream-size-method-in-java-with-examples/)

Java 中 **ByteArrayOutputStream** 类的 **size()** 方法用于获取缓冲区的当前大小。该缓冲区累积在字节数组输出流中。此方法以整数类型返回当前缓冲区的大小。

**语法:**

```
public int size()

```

**参数:**此方法不接受任何参数。

**返回值:**该方法返回当前缓冲区的大小为整数。

**异常:**此方法不抛出任何异常。

以下程序说明了 IO 包中 ByteArrayOutputStream 类中的 size()方法:

**程序 1:**

```
// Java program to illustrate
// ByteArrayOutputStream size() method

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

        for (byte b : buf) {
            // Write byte
            // to byteArrayOutputStream
            byteArrayOutStr.write(b);

            // Print the byteArrayOutputStream
            // as String and size as integer
            System.out.println(
                byteArrayOutStr.toString() + " "
                + byteArrayOutStr.size());
        }
    }
}
```

**Output:**

```
G 1
GE 2
GEE 3
GEEK 4
GEEKS 5

```

**程序 2:**

```
// Java program to illustrate
// ByteArrayOutputStream size() method

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

        for (byte b : buf) {
            // Write byte
            // to byteArrayOutputStream
            byteArrayOutStr.write(b);

            // Convert byteArrayOutputStream
            // into String
            String s
                = byteArrayOutStr.toString();

            int buffsize
                = byteArrayOutStr.size();

            // Print string and size
            System.out.println(
                s + " " + buffsize);
        }
    }
}
```

**Output:**

```
G 1
GE 2
GEE 3
GEEK 4
GEEKS 5
GEEKSF 6
GEEKSFO 7
GEEKSFOR 8
GEEKSFORG 9
GEEKSFORGE 10
GEEKSFORGEE 11
GEEKSFORGEEK 12
GEEKSFORGEEKS 13

```

**参考文献:**
[https://docs . Oracle . com/javase/10/docs/API/Java/io/bytearayoutstream . html # size()](https://docs.oracle.com/javase/10/docs/api/java/io/ByteArrayOutputStream.html#size())