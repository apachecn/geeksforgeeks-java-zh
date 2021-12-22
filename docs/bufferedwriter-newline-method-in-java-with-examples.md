# Java 中 BufferedWriter newLine()方法，带示例

> 原文:[https://www . geeksforgeeks . org/bufferedwriter-new line-method-in-Java-with-examples/](https://www.geeksforgeeks.org/bufferedwriter-newline-method-in-java-with-examples/)

Java 中 **BufferedWriter** 类的 **newLine()** 方法用于将下一行分隔为新行。它用作缓冲写入器流中的写入分隔符。

**语法:**

```
public void newLine()
            throws IOException

```

**参数:**此方法不接受任何参数。

**返回值:**此方法不返回值。

**异常:**如果出现输入输出错误，该方法抛出**异常**。

下面的程序说明了 IO 包中 BufferedWriter 类中的 newLine()方法:

**程序 1:**

```
// Java program to illustrate
// BufferedWriter newLine() method

import java.io.*;

public class GFG {
    public static void main(String[] args)
        throws IOException
    {

        // Create the string Writer
        StringWriter stringWriter
            = new StringWriter();

        // Convert stringWriter to
        // bufferedWriter
        BufferedWriter buffWriter
            = new BufferedWriter(
                stringWriter);

        // Write "A" to buffer writer
        buffWriter.write(65);

        // Revoke newLine() method
        buffWriter.newLine();

        // Write "B" to buffer writer
        buffWriter.write(66);

        buffWriter.flush();

        System.out.println(
            stringWriter.getBuffer());
    }
}
```

**Output:**

```
A
B

```

**程序 2:**

```
// Java program to illustrate
// BufferedWriter newLine() method

import java.io.*;

public class GFG {
    public static void main(String[] args)
        throws IOException
    {
        // Create the string Writer
        StringWriter stringWriter
            = new StringWriter();

        // Convert stringWriter to
        // bufferedWriter
        BufferedWriter buffWriter
            = new BufferedWriter(
                stringWriter);

        // Write "GEEKS" to buffered writer
        buffWriter.write(
            "GEEKSFORGEEKS", 0, 5);

        // Revoke newLine() method
        buffWriter.newLine();

        // Write "GEEKSFORGEEKS"
        // to buffered writer
        buffWriter.write(
            "GEEKSFORGEEKS", 0, 13);

        buffWriter.flush();

        System.out.println(
            stringWriter.getBuffer());
    }
}
```

**Output:**

```
GEEKS
GEEKSFORGEEKS

```

**参考文献:**
[https://docs . Oracle . com/javase/10/docs/API/Java/io/bufferedwriter . html # newLine()](https://docs.oracle.com/javase/10/docs/api/java/io/BufferedWriter.html#newLine())