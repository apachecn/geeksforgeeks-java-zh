# Java 程序打印字符串中的引号

> 原文:[https://www . geesforgeks . org/Java-程序到打印-字符串引号/](https://www.geeksforgeeks.org/java-program-to-print-quotation-marks-in-a-string/)

双引号主要用于表示字符串。当我们打印任何字符串时，不打印双引号，而只打印其中的值。

**方法:**

可以使用下面列出的 java 中的以下方式插入双引号:

1.  Use **to escape the sequence character**
2.  Use the **character**
3.  Use **Unicode character**

让我们详细讨论上面列出的方法，并实现它们，以获得公平的理解。

**方法 1:** 使用转义序列字符

用字符串打印双引号的第一种方法使用转义序列，转义序列是带有字符的反斜杠(\)。它有时也被称为转义字符。我们的目标是在字符串的起点和终点插入双引号。\ '是用于插入双引号的转义序列。

下面我们可以看到，我们在字符串中使用了这个转义序列，输出显示了带有引号的字符串。

**示例**

## Java

```
// Java Program to Print Quotation Marks in a String
// Using Escape Sequence Character

// Importing input output classes
import java.io.*;

// Main class to print quotes
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Custom input string
        String str = " \"Akshit Loves GeeksforGeeks\" ";

        // Print and display the above string on console
        System.out.println(str);
    }
}
```

**输出**

```
 "Akshit Loves GeeksforGeeks" 
```

**方法二:在 Java** 中使用 ***char*** **打印双引号**

我们还可以使用 char 打印字符串的双引号。首先，我们必须将双引号( " )转换成字符。

在下面的例子中，我们有一个单引号，双引号被单引号包围。双引号代表字符串，单引号代表字符。现在，由于我们的双引号已经变成了一个字符，我们可以在开始点和结束点将它与字符串连接起来。

**示例**

## Java

```
// Java Program to Print Quotation Marks in a String
// Using char

// Importing input output classes
import java.io.*;

// Main class to print quotes
public class PrintQuotes {

    // Main driver method
    public static void main(String[] args)
    {

        char value = '"';
        String str
            = value + "Akshit Loves GeeksforGeeks" + value;

        System.out.println(str);
    }
}
```

**输出**

```
"Akshit Loves GeeksforGeeks"
```

**方法 3:** 使用 Unicode 字符

无论何时我们想要打印或使用任何字符，如符号或非英语字符，我们都可以使用 Unicode 字符。每个 Unicode 代表一个字符，而\u0022 代表一个双引号。

我们需要将 Unicode 转换成字符，然后将字符串连接起来。Unicode 字符是通用的字符编码标准。它代表了不同字符在不同文档中的表现方式，如文本文件、网页等。Unicode 支持 4 个字节的字符。UTF-8 已经成为标准字符编码，它支持每个字符 4 个字节。还有其他不同的 Unicode 编码，如 UTF-16、UTF-8。java 中的字符文字是 java 中的常量字符。它们用单引号' A '，' A '，' 1 '，'表示！，'π'，' { content } ' 2019；, ' '.可以存储字符文字的数据类型是 char。

**示例**

## Java

```
public class PrintQuotes {
    public static void main(String[] args) {

        String str = '\u0022' + "Akshit Loves GeeksforGeeks" + '\u0022';
        System.out.println(str);

    }
}
```

**输出**

```
"Akshit Loves GeeksforGeeks"
```