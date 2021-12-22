# 将堆栈跟踪转换为字符串的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-program-to-convert-a-stack-trace-to-a-string/](https://www.geeksforgeeks.org/java-program-to-convert-a-stack-trace-to-a-string/)

以下 Java 编程主题的必备知识:

*   [[Java string]](https://www.geeksforgeeks.org/strings-in-java/)
*   [Java exception handling](https://www.geeksforgeeks.org/exceptions-in-java/)

**将堆栈跟踪转换为字符串**

在下面的程序中，我们通过访问一个越界元素，将 ArrayIndexOutOfBoundsException 放到了我们的程序中。Java StringWriter 类是一个字符流，它从可用于构造字符串的字符串缓冲区中收集输出。Java PrintWriter 类是 java.io 包的一部分，用于以文本形式写入输出数据。在 catch 块中使用 **StringWriter** 和 **PrintWriter** ，其背后的目的是以字符串的形式打印给定的输出。

现在使用异常的 **printStackTrace()** 方法打印堆栈跟踪，然后将其写入写入器。最后，使用 **toString()** 方法将其转换为字符串。

实现:

## Java

```
// Java Program to convert a Stack trace to a string

import java.io.*;

public class PrintStackTrace {

    public static void main(String[] args)
    {

        try {
            int a[] = new int[3];
            System.out.println(
                "Printing element at index four:" + a[4]);
        }
        catch (ArrayIndexOutOfBoundsException e) {
            StringWriter string_writer = new StringWriter();
            e.printStackTrace(
                new PrintWriter(string_writer));

            String printExceptionAsString
                = string_writer.toString();
            System.out.println(printExceptionAsString);
        }
    }
}
```

**输出**

```
java.lang.ArrayIndexOutOfBoundsException: Index 4 out of bounds for length 3
    at PrintStackTrace.main(PrintStackTrace.java:12)

```