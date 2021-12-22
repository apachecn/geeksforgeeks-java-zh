# 将字节数组转换为字符串的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序-转换-字节-数组-字符串/](https://www.geeksforgeeks.org/java-program-to-convert-byte-array-to-string/)

在 Java 中，有多种方法可以将字节数组更改为字符串，您可以使用来自 JDK 的方法，也可以使用开源的补充 API，如 [Apache](https://www.geeksforgeeks.org/apache-poi-getting-started/) commons 和 Google Guava。这些应用编程接口至少提供了两组从字节数组创建字符串的方法；一个使用默认平台编码，另一个采用字符编码。

这也是在任何编程语言中将字节转换为字符时指定字符编码的最佳实践之一。您的字节数组可能包含不可打印的 ASCII 字符。让我们首先看看 JDK 将字节[]转换成字符串的方法。一些程序员还建议使用字符串上的字符集来指定字符编码，例如，使用标准字符集来代替“UTF-8”。UTF 8 主要是为了在最坏的情况下避免不支持的编码异常。

**情况 1:** 无字符编码

我们可以将 ASCII 字符集的字节数组转换为字符串，甚至不需要指定字符编码。想法是将字节[]传递给字符串。如下例所示:

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Convert Byte Array to String
// Without character encoding

// Importing required classes
import java.io.IOException;
import java.util.Arrays;

// Main class
class GFG {
    // Main driver method
    public static void main(String[] args)
        throws IOException
    {
        // Getting bytes from the custom input string
        // using getBytes() method and
        // storing it in a byte array
        byte[] bytes = "Geeksforgeeks".getBytes();

        System.out.println(Arrays.toString(bytes));

        // Creating a string from the byte array
        // without specifying character encoding
        String string = new String(bytes);

        // Printing the string
        System.out.println(string);
    }
}
```

**Output**

```java
[71, 101, 101, 107, 115, 102, 111, 114, 103, 101, 101, 107, 115]
Geeksforgeeks
```

**情况 2:** 带字符编码

我们知道一个字节包含 8 位，最多可以有 256 个不同的值。对于 ASCII 字符集来说，这很好，只使用前 7 位。对于超过 256 个值的字符集，我们应该明确指定编码，它告诉如何将字符编码成字节序列。

> **注意:**这里我们使用的是[标准字符集。UTF_8](https://www.geeksforgeeks.org/sha-256-hash-in-java/) 指定编码。在 Java 7 之前，我们可以使用字符集。对于名称(“UTF-8”)。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Convert Byte Array to String
// With character encoding

// Importing required classes
import java.io.IOException;
import java.nio.charset.StandardCharsets;

// Main class
class GFG {

    // Main driver method
    public static void main(String[] args)
        throws IOException
    {

        // Custom input string is converted into array of
        // bytes and stored
        byte[] bytes = "Geeksforgeeks".getBytes(
            StandardCharsets.UTF_8);

        // Creating a string from the byte array with
        // "UTF-8" encoding
        String string
            = new String(bytes, StandardCharsets.UTF_8);

        // Print and display the string
        System.out.println(string);
    }
}
```

**Output**

```java
Geeksforgeeks
```

这就是将字节数组转换为 Java 字符串的全部内容。

> **结论:**在 Java 中处理 byte[]数组和 String 之间的转换时，我们应该关注输入数据的类型。
> 
> *   当输入的数据是字符串或文本内容时，请使用字符串类。
> *   在字节数组中输入数据时，请使用 Base64 类。