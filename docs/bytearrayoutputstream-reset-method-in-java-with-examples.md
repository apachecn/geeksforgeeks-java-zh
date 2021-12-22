# Java 中的 ByteArrayOutputStream reset()方法，示例

> 原文:[https://www . geeksforgeeks . org/bytearayoputstream-reset-method-in-Java-with-examples/](https://www.geeksforgeeks.org/bytearrayoutputstream-reset-method-in-java-with-examples/)

Java 中 **ByteArrayOutputStream** 类的 **reset()** 方法用于重置 BytearrayOutStream，并使该 BytearrayOutStream 的计数字段为零。因此，字节数组输出流中所有当前累积的输出都将被丢弃。通过重用已经分配的缓冲区空间，可以再次使用这个字节数组输出流。

**语法:**

```
public void reset()

```

**参数:**此方法不接受任何参数。

**返回值:**此方法不返回值。

**异常:**此方法不抛出任何异常。

下面的程序说明了 IO 包中 ByteArrayOutputStream 类中的 reset()方法:

**程序 1:**

```
// Java program to illustrate
// ByteArrayOutputStream reset() method

import java.io.*;

public class GFG {
    public static void main(String[] args)
        throws Exception
    {

        // Create byteArrayOutputStream
        ByteArrayOutputStream byteArrayOutStr
            = new ByteArrayOutputStream();

        // Create two byte arrays
        byte[] buf1 = { 65, 66, 67, 68, 69 };
        byte[] buf2 = { 71, 69, 69, 75, 83 };

        // Write first byte array
        // to byteArrayOutputStream
        byteArrayOutStr.write(buf1);

        // Print the byteArrayOutputStream
        // as String
        System.out.println(
            byteArrayOutStr.toString());

        // reset() is called
        byteArrayOutStr.reset();

        // Write second byte array
        // to byteArrayOutputStream
        byteArrayOutStr.write(buf2);

        // Print the byteArrayOutputStream
        // as String
        System.out.println(
            byteArrayOutStr.toString());
    }
}
```

**Output:**

```
ABCDE
GEEKS

```

**程序 2:**

```
// Java program to illustrate
// ByteArrayOutputStream reset() method

import java.io.*;

public class GFG {
    public static void main(String[] args)
        throws Exception
    {

        // Create byteArrayOutputStream
        ByteArrayOutputStream byteArrayOutStr
            = new ByteArrayOutputStream();

        // Create two byte arrays
        byte[] buf1 = { 71, 69, 69, 75, 83 };
        byte[] buf2 = { 70, 79, 82 };

        // Write first byte array
        // to byteArrayOutputStream
        byteArrayOutStr.write(buf1);

        // Print the byteArrayOutputStream
        // as String
        System.out.println(
            byteArrayOutStr.toString());

        // reset() is called
        byteArrayOutStr.reset();

        // Write second byte array
        // to byteArrayOutputStream
        byteArrayOutStr.write(buf2);

        // Print the byteArrayOutputStream
        // as String
        System.out.println(
            byteArrayOutStr.toString());

        // reset() is called
        byteArrayOutStr.reset();

        // Write first byte array
        // to byteArrayOutputStream
        byteArrayOutStr.write(buf1);

        // Print the byteArrayOutputStream
        // as String
        System.out.println(
            byteArrayOutStr.toString());
    }
}
```

**Output:**

```
GEEKS
FOR
GEEKS

```

**参考资料:**
[https://docs . Oracle . com/javae/10/docs/API/Java/io/bytearray output stream . html # reset()](https://docs.oracle.com/javase/10/docs/api/java/io/ByteArrayOutputStream.html#reset())