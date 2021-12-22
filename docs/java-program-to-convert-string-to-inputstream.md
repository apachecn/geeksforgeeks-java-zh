# 将字符串转换为输入流的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-program-to-convert-string-to-inputstream/](https://www.geeksforgeeks.org/java-program-to-convert-string-to-inputstream/)

给定一个字符串**，**，任务是将该字符串转换为 InputStream，如下图所示。

插图:

```java
Input  : String : "Geeks for Geeks"
Output : Input Stream : Geeks for Geeks 
```

```java
Input  : String : "A computer science portal"
Output : Input stream :  A computer science portal 
```

为了达到目标，我们需要使用 ByteArrayInputStream。那么让我们来讨论它是如何做到的？

我们可以通过使用字节数组输入流类将字符串转换为输入流对象。ByteArrayInputStream 是 InputStream 类中的一个子类。在 ByteArrayInputStream 中，有一个包含从流中读取的字节的内部缓冲区。

**进场:**

1.  获取字符串的字节数。
2.  使用字符串的字节创建一个新的字节数组
3.  将字节数组输入流对象分配给输入流变量。
4.  缓冲区包含从流中读取的字节。
5.  打印输入流。

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Convert String to InputStream
// Using ByteArrayInputStream
// Importing required libraries
import java.io.*;
import java.io.BufferedReader;
import java.io.ByteArrayInputStream;
import java.io.IOException;
import java.io.InputStream;
import java.io.InputStreamReader;
import java.nio.charset.Charset;

// Main class
public class GFG {

    // main driver method
    public static void main(String[] args) throws IOException {
        // Custom inout string as an input
        String string = "Geeks for Geeks";

        // Printing the above string
        System.out.print("String : " + string);

        // Now, using ByteArrayInputStream to
        // get the bytes of the string, and
        // converting them to InputStream
        InputStream stream = new ByteArrayInputStream(string.getBytes
                (Charset.forName("UTF-8")));

        // Creating an object of BufferedReader class to
        // take input
        BufferedReader br = new BufferedReader(new InputStreamReader(stream));

        // Printing the input stream
        // using rreadLine() method
        String str = br.readLine();

        System.out.print("\nInput stream : ");

        // If string is not NULL
        while (str != null) {
            // Keep taking input
            System.out.println(str);
            str = br.readLine();
        }
    }
}
```

**Output**

```java
String : Geeks for Geeks
Input stream : Geeks for Geeks
```