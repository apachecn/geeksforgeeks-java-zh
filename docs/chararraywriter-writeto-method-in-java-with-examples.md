# Java 中 CharArrayWriter writeTo()方法，带示例

> 原文:[https://www . geeksforgeeks . org/chararraywriter-write to-method-in-Java-with-examples/](https://www.geeksforgeeks.org/chararraywriter-writeto-method-in-java-with-examples/)

Java 中 **CharArrayWriter** 类的 **writeTo(Writer)** 方法用于将 CharArrayWriter 的内容写入另一个字符流。
**语法:**

```
public void writeTo(Writer out)
             throws IOException

```

**参数:**该方法接受一个参数**输出**，该参数代表作为目标流的输出流。
**返回值:**此方法不返回值。
**异常:**如果出现输入输出错误，该方法抛出 **IOException** 。
下面的程序说明了 IO 包中 CharArrayWriter 类的 writeTo(Writer)方法:
**程序 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to illustrate
// CharArrayWriter writeTo(Writer) method

import java.io.*;

public class GFG {
    public static void main(String[] args)
        throws IOException
    {

        // Create charArrayWriter
        CharArrayWriter charArrayWriter
            = new CharArrayWriter();

        String str = "GEEKS";

        charArrayWriter.write(str);

        // Create outputStream
        CharArrayWriter out
            = new CharArrayWriter();

        charArrayWriter.writeTo(out);

        // print the outputStream
        System.out.println(
            out.toString());
    }
}
```

**Output:**

```
GEEKS

```

**节目 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to illustrate
// CharArrayWriter writeTo(Writer) method

import java.io.*;

public class GFG {
    public static void main(String[] args)
        throws IOException
    {

        // Create charArrayWriter
        CharArrayWriter charArrayWriter
            = new CharArrayWriter();

        charArrayWriter.write("GEEKSFORGEEKS");

        // Create outputStream
        CharArrayWriter out
            = new CharArrayWriter();

        charArrayWriter.writeTo(out);

        // print the outputStream
        System.out.println(
            out.toString());
    }
}
```

**Output:**

```
GEEKSFORGEEKS

```

**参考文献:**
[https://docs . Oracle . com/javase/10/docs/API/Java/io/chararraywriter . html # write to(Java . io . writer)](https://docs.oracle.com/javase/10/docs/api/java/io/CharArrayWriter.html#writeTo(java.io.Writer))