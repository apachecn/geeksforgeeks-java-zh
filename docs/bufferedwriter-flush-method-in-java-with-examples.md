# Java 中的 BufferedWriter flush()方法，示例

> 原文:[https://www . geeksforgeeks . org/bufferedwriter-flush-in-Java-method-with-examples/](https://www.geeksforgeeks.org/bufferedwriter-flush-method-in-java-with-examples/)

Java 中 **BufferedWriter** 类的 **flush()** 方法用于从缓冲的编写器流中刷新字符。

**语法:**

```
public void flush()
            throws IOException

```

**指定者:**该方法由**可冲**界面的冲()方法指定。

**覆盖:**该方法覆盖 **Writer** 类的 flush()方法。

**参数:**此方法不接受任何参数。

**返回值:**此方法不返回值。

**异常:**如果出现输入输出错误，该方法抛出**异常**。

下面的程序说明了 IO 包中 BufferedWriter 类中的 flush()方法:

**程序 1:**

```
// Java program to illustrate
// BufferedWriter flush() method

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

        // Write "GEEKS" to buffer writer
        buffWriter.write(
            "GEEKSFORGEEKS", 0, 5);

        // Flush the buffer writer
        buffWriter.flush();

        System.out.println(
            stringWriter.getBuffer());
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
// BufferedWriter flush() method

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

        // Flush the buffered writer
        buffWriter.flush();

        System.out.println(
            stringWriter.getBuffer());

        // Write "GEEKSFORGEEKS"
        // to buffered writer
        buffWriter.write(
            "GEEKSFORGEEKS", 5, 8);

        // Flush the buffered writer
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
[https://docs . Oracle . com/javase/10/docs/API/Java/io/bufferedwriter . html # flush()](https://docs.oracle.com/javase/10/docs/api/java/io/BufferedWriter.html#flush())