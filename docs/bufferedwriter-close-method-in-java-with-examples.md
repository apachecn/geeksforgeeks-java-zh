# Java 中的 BufferedWriter close()方法，示例

> 原文:[https://www . geeksforgeeks . org/bufferedwriter-close-method-in-Java-with-examples/](https://www.geeksforgeeks.org/bufferedwriter-close-method-in-java-with-examples/)

Java 中 **BufferedWriter** 类的 **close()** 方法用于从缓冲流中刷新字符，然后将其关闭。一旦流关闭，进一步调用 write()和 append()等方法将引发异常。

**语法:**

```java
public void close()

```

**参数:**此方法不接受任何参数。

**返回值:**此方法不返回值。

**异常:**如果出现输入输出错误，该方法抛出**异常**。

下面的程序说明了 IO 包中 BufferedWriter 类中的 close()方法:

**程序 1:**

```java
// Java program to illustrate
// BufferedWriter close() method

import java.io.*;

public class GFG {
    public static void main(String[] args)
    {
        try {

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

            // Close the buffered writer
            buffWriter.close();

            System.out.println(
                stringWriter.getBuffer());
        }
        catch (Exception e) {
            System.out.println(
                "BufferedWriter is closed");
        }
    }
}
```

**输出:**

```java
GEEKS

```

**程序二:**

```java
// Java program to illustrate
// BufferedWriter close() method

import java.io.*;

public class GFG {
    public static void main(String[] args)
    {
        try {

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

            // Close the buffered writer
            buffWriter.close();

            System.out.println(
                stringWriter.getBuffer());

            // It will throw exception
            buffWriter.write(
                "GEEKSFORGEEKS", 5, 8);
        }
        catch (Exception e) {
            System.out.println(
                "BufferedWriter is closed");
        }
    }
}
```

**输出:**

```java
GEEKS
BufferedWriter is closed

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/io/bufferedwriter . html # close()](https://docs.oracle.com/javase/7/docs/api/java/io/BufferedWriter.html#close())