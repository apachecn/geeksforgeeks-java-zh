# 用 Java 写 BufferedWriter()方法，示例

> 原文:[https://www . geeksforgeeks . org/bufferedwriter-write-method-in-Java-with-examples/](https://www.geeksforgeeks.org/bufferedwriter-write-method-in-java-with-examples/)

Java 中 **BufferedWriter** 类中的 **write()** 方法有三种使用方式:

1.Java 中 **BufferedWriter** 类的 **write(int)** 方法用于在缓冲区写入器流中一次写入一个字符。

**语法:**

```java
public void write(int ch)
            throws IOException

```

**覆盖:**该方法覆盖 **Writer** 类的 write()方法。

**参数:**该方法接受单个参数 ch，表示要写入的字符。

**返回值:**此方法不返回值。

**异常:**如果出现输入输出错误，该方法抛出**异常**。

下面的程序说明了 IO 包中 BufferedWriter 类的 write(int)方法:

**程序:**

```java
// Java program to illustrate
// BufferedWriter write(int) method

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

        // Write "G" to buffer writer
        buffWriter.write(71);

        // Write "E" to buffer writer
        buffWriter.write(69);

        // Write "E" to buffer writer
        buffWriter.write(69);

        // Write "K" to buffer writer
        buffWriter.write(75);

        // Write "S" to buffer writer
        buffWriter.write(83);

        buffWriter.flush();

        System.out.println(
            stringWriter.getBuffer());
    }
}
```

**Output:**

```java
GEEKS

```

2.Java 中 **BufferedWriter** 类的 **write(String s，int off，int len)** 方法用于在缓冲区写入器流中写入作为参数传递的字符串的一部分。

**语法:**

```java
public void write(String s,
                  int off,
                  int len)
           throws IOException

```

**覆盖:**该方法覆盖 **Writer** 类的 write()方法。

**参数:**该方法接受三个参数:

*   **s**–它代表字符串，字符串的一部分将被写入。
*   **off**–表示开始写入的字符串中的索引。
*   **len**–表示要写入的字符串部分的长度。

**返回值:**此方法不返回值。

**异常:**

*   **IndexOutOfBoundsException**–如果传递的索引为负或者传递的部分长度大于给定字符串的长度，则此方法将引发 indexout of boundsexception。
*   **IOException**–如果出现 IO 错误，该方法抛出 IO exception。

**注意:**如果字符串(len)部分的长度为负或者 index 为负，则该方法应该抛出 IndexOutOfBoundsException，但在这些情况下，该方法不会抛出这样的异常。在这种情况下，它不写字符，而是抛出异常。

下面的程序说明了 IO 包中 BufferedWriter 类的写(字符串)方法:

**程序:**

```java
// Java program to illustrate
// BufferedWriter write(String) method

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

        buffWriter.flush();

        System.out.println(
            stringWriter.getBuffer());
    }
}
```

**Output:**

```java
GEEKS

```

3.Java 中 **BufferedWriter** 类的 **write(char[ ] cbuf，int off，int len)** 方法用于在缓冲区写入器流中写入作为参数传递的字符数组的一部分。此方法通常将数组中的字符存储到流中，并将缓冲区刷新到主流。当缓冲区长度等于数组长度时，可以直接使用主流。

**语法:**

```java
public void write(char[ ] cbuf,
                  int off,
                  int len)
           throws IOException

```

**指定者:**此方法由 **Writer** 类的 write()方法指定。

**参数:**该方法接受三个参数:

*   **cbuf**–表示字符数组，字符的一部分要被写入。
*   **off**–表示开始写入的数组的索引。
*   **len**–表示要写入的数组部分的长度。

**返回值:**此方法不返回值。

**异常:**

*   **IndexOutOfBoundsException**–如果传递的索引为负或传递的部分长度大于给定字符数组的长度，则此方法将引发 IndexOutOfBoundsException。
*   **IOException**–如果出现 IO 错误，该方法抛出 IO exception。

下面的程序说明了 IO 包中 BufferedWriter 类的 write(char[ ])方法:

**程序:**

```java
// Java program to illustrate
// BufferedWriter write(char[ ]) method

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
        // Create character array
        char cbuf[] = { 'G', 'E', 'E', 'K',
                        'S', 'F', 'O', 'R' };

        // Write "GEEKS" to buffer writer
        buffWriter.write(cbuf, 0, 5);

        // Write "FOR" to buffer writer
        buffWriter.write(cbuf, 5, 3);

        // Again write "GEEKS" to buffer writer
        buffWriter.write(cbuf, 0, 5);

        buffWriter.flush();

        System.out.println(
            stringWriter.getBuffer());
    }
}
```

**Output:**

```java
GEEKSFORGEEKS

```

**参考文献:**
1。[https://docs . Oracle . com/javase/10/docs/API/Java/io/bufferedwriter . html # write(int)](https://docs.oracle.com/javase/10/docs/api/java/io/BufferedWriter.html#write(int))
2。[https://docs . Oracle . com/javase/10/docs/API/Java/io/bufferedwriter . html # write(Java . lang . string，int，int)](https://docs.oracle.com/javase/10/docs/api/java/io/BufferedWriter.html#write(java.lang.String, int, int))
3。[https://docs . Oracle . com/javase/10/docs/API/Java/io/bufferedwriter . html # write(char % 5B % 5D，int，int)](https://docs.oracle.com/javase/10/docs/api/java/io/BufferedWriter.html#write(char%5B%5D, int, int))