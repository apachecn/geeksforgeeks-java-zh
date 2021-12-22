# Java 中的 ByteArrayOutputStream toString()方法，示例

> 原文:[https://www . geeksforgeeks . org/bytearlayoutputstream-tostring-method-in-Java-with-examples/](https://www.geeksforgeeks.org/bytearrayoutputstream-tostring-method-in-java-with-examples/)

Java 中 **ByteArrayOutputStream** 类的 **toString()** 方法有两种使用方式:

1.Java 中 **ByteArrayOutputStream** 类的 **toString()** 方法用于将 ByteArrayOutputStream 的缓冲区内容转换为字符串。此方法使用系统的默认字符集。新获得的字符串的长度可能因缓冲区大小而异。该方法用默认替换字符串替换格式错误的输入和不可映射的字符序列。

**语法:**

```
public String toString()

```

**覆盖:**该方法覆盖**对象**类的 [toString()方法。](https://www.geeksforgeeks.org/object-tostring-method-in-java/)

**参数:**此方法不接受任何参数。

**返回值:**该方法返回从缓冲区内容中获取的字符串。

**异常:**此方法不抛出任何异常。

下面的程序说明了 IO 包中 ByteArrayOutputStream 类中的 toString()方法:

**程序:**

```
// Java program to illustrate
// ByteArrayOutputStream toString() method

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

        // Write byte array
        // to byteArrayOutputStream
        byteArrayOutStr.write(buf);

        // Revoke toString() method
        String str = byteArrayOutStr.toString();

        // Print the string
        System.out.println(str);
    }
}
```

**Output:**

```
GEEKS

```

2.Java 中 **ByteArrayOutputStream** 类的 **toString(字符串字符集名)**方法用于使用指定的字符集名将 ByteArrayOutputStream 的缓冲区内容转换为字符串，该字符串作为字符串传递给该方法。

**语法:**

```
public String toString(String charsetName)
      throws UnsupportedEncodingException

```

**参数:**该方法接受一个参数作为字符串，代表支持的字符集的名称。

**返回值:**该方法使用支持的字符集返回从缓冲区内容获得的字符串。

**异常:**如果不支持字符集的名称，该方法将抛出**不支持的异常**。

下面的程序说明了输入输出包中字节数组输出流类中的字符串方法:

**程序 1:**

```
// Java program to illustrate
// ByteArrayOutputStream
// toString(String charsetName) method

import java.io.*;

public class GFG {
    public static void main(String[] args)
        throws Exception
    {
        try {
            // Create byteArrayOutputStream
            ByteArrayOutputStream byteArrayOutStr
                = new ByteArrayOutputStream();

            // Create byte array
            byte[] buf = { 71, 69, 69, 75, 83 };

            // Write byte array
            // to byteArrayOutputStream
            byteArrayOutStr.write(buf);

            // Revoke toString(String) method
            String str
                = byteArrayOutStr
                      .toString("UTF-8");

            // Print the string
            System.out.println(str);
        }
        catch (Exception e) {
            System.out.println(
                "CharsetName not supported");
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
// ByteArrayOutputStream
// toString(String charsetName) method

import java.io.*;

public class GFG {
    public static void main(String[] args)
        throws Exception
    {
        try {
            // Create byteArrayOutputStream
            ByteArrayOutputStream byteArrayOutStr
                = new ByteArrayOutputStream();

            // Create byte array
            byte[] buf = { 71, 69, 69, 75, 83 };

            // Write byte array
            // to byteArrayOutputStream
            byteArrayOutStr.write(buf);

            // Revoke toString(String charsetName)
            // method
            String str
                = byteArrayOutStr.toString("XYZ");

            // Print the string
            System.out.println(str);
        }
        catch (Exception e) {
            System.out.println(
                "CharsetName not supported");
        }
    }
}
```

**Output:**

```
CharsetName not supported

```

**参考资料:**
1。[https://docs . Oracle . com/javae/10/docs/API/Java/io/bytearray output stream . html # tostring()](https://docs.oracle.com/javase/10/docs/api/java/io/ByteArrayOutputStream.html#toString())t5]2。[https://docs . Oracle . com/javae/10/docs/API/Java/io/bytearray output stream . html # tostring(Java . lang . string)](https://docs.oracle.com/javase/10/docs/api/java/io/ByteArrayOutputStream.html#toString(java.lang.String))