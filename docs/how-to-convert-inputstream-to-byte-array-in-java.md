# 如何在 Java 中将 InputStream 转换成字节数组？

> 原文:[https://www . geesforgeks . org/如何将 java 中的 inputstream 转换为字节数组/](https://www.geeksforgeeks.org/how-to-convert-inputstream-to-byte-array-in-java/)

在 Java 中，输入流是指字节形式的有序数据流。这种数据流可能来自各种资源，如文件、网络程序、输入设备等。为了读取这样的数据，我们在 Java IO API 中有一个 Java [**InputStream**](https://www.geeksforgeeks.org/java-io-inputstream-class-in-java/) 类。有几种方法可以将此输入流转换为字节数组(或字节[])，以便在需要时使用。我们现在来看一些方法，如下所示:

**方法:**

1.  使用 read(byte[])或 readAllBytes()
2.  使用字节数组输出流类
3.  使用字节流实用程序类
4.  使用 Apache 公共输入输出库

现在，我们将详细讨论每一种方法，并通过干净的 java 程序理解相同的实现，如下所示:

**方法 1:** 使用 read(byte[])或 readAllBytes()

在 [InputStream 类](https://www.geeksforgeeks.org/java-io-inputstream-class-in-java/)中，我们有一个 read()方法，可以将一个字节数组作为参数传递，得到字节数组形式的输入流数据。但是这种方法有一个缺点，它最多只能读取作为参数传递的数组大小的数据。只有我们事先知道传入数据的大小，它才能正常工作。方法返回一个 int 值，该值等于读入数组的字节数，如果到达流结尾，则返回-1。

**语法:**

已读取声明(字节[])

```java
public int read​(byte[] byteArray)
throws IOException
```

为了克服必须事先知道输入大小的缺点，从 Java 9 开始，我们有了另一个名为 [*readAllBytes()*](https://www.geeksforgeeks.org/file-readallbytes-method-in-csharp-with-examples/) 的方法。这个方法可以读取输入流中所有可用的字节。该方法在将输入流转换为字节数组时更快、更有效。

**语法:** readAllBytes()

```java
public byte[] readAllBytes()
throws IOException
```

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Convert InputStream to Byte Array
// Using read(byte[]) or readAllBytes()

// Importing required classes
import java.io.*;
import java.nio.charset.StandardCharsets;

// Main class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Creating a Input Stream here
        // Usually it comes from files, programs
        InputStream inputStream = new ByteArrayInputStream(
            "GeeksForGeeks".getBytes(
                StandardCharsets.UTF_8));

        // Taking the InputStream data into a byte array
        byte[] byteArray = null;

        // Try block to check for exceptions
        try {
            byteArray = inputStream.readAllBytes();
        }

        // Catch block to handle the exceptions
        catch (IOException e) {

            // Print and dispal ythe exceptions
            System.out.println(e);
        }

        // Iterating over using for each loop
        for (byte b : byteArray)

            // Printing the content of byte array
            System.out.print((char)b + " ");
    }
}
```

**Output**

```java
G e e k s F o r G e e k s 
```

**示例 2:** 使用字节数组输出流类

这是一种将输入流数据转换为字节数组的间接方法。这里我们将使用 ByteArrayOutputStream 类的一个对象作为缓冲区。为此，我们从输入流类中读取每个字节，并将其写入字节数组输出流类。稍后我们调用 toByteArray()，它以字节数组的形式返回输出流。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Convert InputStream to Byte Array
// Using ByteArrayOutputStream Class

// Importing required classes
import java.io.*;
import java.nio.charset.StandardCharsets;

// Main class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Creating a Input Stream here (usually it comes
        // from files, programs, etc.)
        InputStream inputStream = new ByteArrayInputStream(
            "GeeksForGeeks".getBytes(
                StandardCharsets.UTF_8));

        // Taking the InputStream data into a byte array
        // output stream

        // Buffer size taken to be 1000 say.
        byte[] buffer = new byte[1000];

        // Creating an object of ByteArrayOutputStream class
        ByteArrayOutputStream byteArrayOutputStream
            = new ByteArrayOutputStream();

        // Try block to check for exceptions
        try {
            int temp;

            while ((temp = inputStream.read(buffer))
                   != -1) {
                byteArrayOutputStream.write(buffer, 0,
                                            temp);
            }
        }

        // Catch block to handle the exceptions
        catch (IOException e) {

            // Display the exception/s on the console
            System.out.println(e);
        }

        // Mow converting byte array output stream to byte
        // array
        byte[] byteArray
            = byteArrayOutputStream.toByteArray();

        // Iterating over using for each loop
        for (byte b : byteArray)

            // Printing the content of byte array
            System.out.print((char)b + " ");
    }
}
```

**Output**

```java
G e e k s F o r G e e k s 
```

**方法 3:** 使用字节流实用程序类

[番石榴库](https://www.geeksforgeeks.org/guava-library-java/)中的字节流实用程序类有一个将输入流转换成字节数组的直接方法。

谷歌番石榴是一套 [<u>Java</u>](https://www.geeksforgeeks.org/java/) 的开源 (一种鼓励开放协作的去中心化软件开发模式)公共库，主要由谷歌工程师开发。它有助于减少编码错误。它为集合、缓存、原语支持、并发性、公共注释、字符串处理、输入/输出和验证提供了实用方法。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Convert InputStream to Byte Array
// Using ByteArrayOutputStream Class

// Importing required classes, here additionally
// We are importing from Guava Library
import com.google.common.io.ByteStreams;
import java.io.*;
import java.nio.charset.StandardCharsets;

// Main class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Creating a Input Stream here
        // usually it comes from files, programs
        InputStream inputStream = new ByteArrayInputStream(
            "GeeksForGeeks".getBytes(
                StandardCharsets.UTF_8));

        // Taking the InputStream data into a byte array
        // using ByteStreams
        byte[] byteArray = null;

        // Try block to check for exceptions
        try {
            byteArray
                = ByteStreams.toByteArray(inputStream);
        }

        // Catch block to handle the exceptions
        catch (IOException e) {

            // Display the exceptions on the console window
            System.out.println(e);
        }

        // Iterating over using for each loop
        for (byte b : byteArray)

            // Printing the content of byte array
            System.out.print((char)b + " ");
    }
}
```

**方法 4:** 使用 [Apache Commons IO 库](https://www.geeksforgeeks.org/implement-how-to-load-file-as-inputstream-in-java/)

这个方法非常类似于使用字节流类。在这里，我们使用了 IOUtils 类，它有一个类似的方法，名为 toByteArray()，将 inputstream 数据作为字节数组返回。用法相同我们只需要使用导入[*org . Apache . commons . io . ioutils*](https://www.geeksforgeeks.org/implement-how-to-load-file-as-inputstream-in-java/)而不是番石榴图书馆的字节流。

**语法:**

```java
byte[] byteArray = IOUtils.toByteArray(inputStream); 
```

> **注意:**但是，这种方法往往需要在编辑器中加入依赖项。