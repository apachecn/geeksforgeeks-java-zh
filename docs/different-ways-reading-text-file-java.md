# 用 Java 读取文本文件的不同方式

> 原文:[https://www . geesforgeks . org/different-way-reading-text-file-Java/](https://www.geeksforgeeks.org/different-ways-reading-text-file-java/)

有多种方法可以读写文本文件。在处理许多应用程序时，这是必需的。有几种方法可以读取 Java 中的纯文本文件，例如，您可以使用[文件阅读器](https://www.geeksforgeeks.org/file-handling-java-using-filewriter-filereader/)、[buffere reader](https://www.geeksforgeeks.org/java-io-bufferedreader-class-java/)或[扫描仪](https://www.geeksforgeeks.org/scanner-class-in-java/)来读取文本文件。每个实用程序都提供一些特殊的功能，例如 BufferedReader 为快速读取提供数据缓冲，Scanner 提供解析功能。

**方法:**

1.  使用 BufferedReader 类
2.  使用扫描仪类
3.  使用文件读取器类
4.  读取列表中的整个文件
5.  以字符串形式读取文本文件

> 我们还可以使用 BufferReader 和 Scanner 在 Java 中逐行读取文本文件。然后 Java SE 8 引入了另一个 Stream 类 **java.util.stream.Stream** ，它提供了一种懒惰且更高效的读取文件的方式。

> **提示注意:**为了让初学者更好地理解代码，避免了像刷新/关闭流、异常处理等编写好代码的做法。

让我们更深入地讨论上述每一种方法，最重要的是通过一个干净的 java 程序来实现它们。

**方法 1:** [使用 BufferedReader 类](https://www.geeksforgeeks.org/java-io-bufferedreader-class-java/)

此方法从字符输入流中读取文本。它可以缓冲字符、数组和行的有效读取。可以指定缓冲区大小，也可以使用默认大小。对于大多数目的来说，默认值足够大。通常，读取器发出的每个读请求都会导致底层字符或字节流发出相应的读请求。因此，建议在读取()操作可能代价高昂的任何读取器(如文件读取器和输入流读取器)周围包装一个缓冲区读取器，如下所示:

```java
BufferedReader in = new BufferedReader(Reader in, int size);
```

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to illustrate Reading from FileReader
// using BufferedReader Class

// Importing input output classes
import java.io.*;

// Main class
public class GFG {

    // main driver method
    public static void main(String[] args) throws Exception
    {

        // File path is passed as parameter
        File file = new File(
            "C:\\Users\\pankaj\\Desktop\\test.txt");

        // Note:  Double backquote is to avoid compiler
        // interpret words
        // like \test as \t (ie. as a escape sequence)

        // Creating an object of BufferedReader class
        BufferedReader br
            = new BufferedReader(new FileReader(file));

        // Declaring a string variable
        String st;
        // Consition holds true till
        // there is character in a string
        while ((st = br.readLine()) != null)

            // Print the string
            System.out.println(st);
    }
}
```

**输出:**

```java
If you want to code refer to GeeksforGeeks
```

**方法 2:** [使用文件阅读器类](https://www.geeksforgeeks.org/difference-between-bufferedreader-and-filereader-in-java/)

读取字符文件的便利类。这个类的构造函数假定默认的字符编码和默认的字节缓冲区大小是合适的。

此类中定义的构造函数如下:

1.  **文件阅读器(文件文件):**给定要读取的文件，创建一个新的文件阅读器
2.  **文件阅读器(文件描述符 fd):** 给定要读取的文件描述符，创建一个新的文件阅读器
3.  **文件阅读器(字符串文件名):**给定要读取的文件的名称，创建一个新的文件阅读器

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Illustrate reading from
// FileReader using FileReader class

// Importing input output classes
import java.io.*;

// Main class
// ReadingFromFile
public class GFG {

    // Main driver method
    public static void main(String[] args) throws Exception
    {

        // Passing the path to the file as a parameter
        FileReader fr = new FileReader(
            "C:\\Users\\pankaj\\Desktop\\test.txt");

        // Declaring loop variable
        int i;
        // Holds true till there is nothing to read
        while ((i = fr.read()) != -1)

            // Print all the content of a file
            System.out.print((char)i);
    }
}
```

**输出:**

```java
If you want to code refer to GeeksforGeeks
```

**方法 3:** [使用扫描仪类](https://www.geeksforgeeks.org/scanner-class-in-java/)

一个简单的文本扫描器，可以使用正则表达式解析基本类型和字符串。扫描仪使用分隔符模式将其输入分成标记，默认情况下，分隔符模式匹配空白。然后，可以使用各种后续方法将结果令牌转换为不同类型的值。

**示例 1:** 使用循环

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to illustrate
// reading from Text File
// using Scanner Class
import java.io.File;
import java.util.Scanner;
public class ReadFromFileUsingScanner
{
  public static void main(String[] args) throws Exception
  {
    // pass the path to the file as a parameter
    File file = new File("C:\\Users\\pankaj\\Desktop\\test.txt");
    Scanner sc = new Scanner(file);

    while (sc.hasNextLine())
      System.out.println(sc.nextLine());
  }
}
```

**输出:**

```java
If you want to code refer to GeeksforGeeks
```

**示例 2:** 不使用循环

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to illustrate reading from FileReader
// using Scanner Class reading entire File
// without using loop
import java.io.File;
import java.io.FileNotFoundException;
import java.util.Scanner;

public class ReadingEntireFileWithoutLoop
{
  public static void main(String[] args)
                        throws FileNotFoundException
  {
    File file = new File("C:\\Users\\pankaj\\Desktop\\test.txt");
    Scanner sc = new Scanner(file);

    // we just need to use \\Z as delimiter
    sc.useDelimiter("\\Z");

    System.out.println(sc.next());
  }
}
```

**输出:**

```java
If you want to code refer to GeeksforGeeks
```

**方法 4:** 读取列表中的整个文件

读取文件中的所有行。此方法确保在读取所有字节或引发输入/输出错误或其他运行时异常时关闭文件。使用指定的字符集将文件中的字节解码为字符。

**语法:**

```java
public static List readAllLines(Path path,Charset cs)throws IOException
```

此方法将以下内容识别为行终止符:

```java
\u000D followed by \u000A, CARRIAGE RETURN followed by LINE FEED
\u000A, LINE FEED
\u000D, CARRIAGE RETURN
```

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to illustrate reading data from file
// using nio.File
import java.util.*;
import java.nio.charset.StandardCharsets;
import java.nio.file.*;
import java.io.*;
public class ReadFileIntoList
{
  public static List<String> readFileInList(String fileName)
  {

    List<String> lines = Collections.emptyList();
    try
    {
      lines =
       Files.readAllLines(Paths.get(fileName), StandardCharsets.UTF_8);
    }

    catch (IOException e)
    {

      // do something
      e.printStackTrace();
    }
    return lines;
  }
  public static void main(String[] args)
  {
    List l = readFileInList("C:\\Users\\pankaj\\Desktop\\test.java");

    Iterator<String> itr = l.iterator();
    while (itr.hasNext())
      System.out.println(itr.next());
  }
}
```

**输出:**

```java
If you want to code refer to GeeksforGeeks
```

**方法 5:** 以字符串形式读取文本文件

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to illustrate
// reading from text file
// as string in Java
package io;

import java.nio.file.*;;

public class ReadTextAsString {

  public static String readFileAsString(String fileName)throws Exception
  {
    String data = "";
    data = new String(Files.readAllBytes(Paths.get(fileName)));
    return data;
  }

  public static void main(String[] args) throws Exception
  {
    String data = readFileAsString("C:\\Users\\pankaj\\Desktop\\test.java");
    System.out.println(data);
  }
}
```

**输出:**

```java
If you want to code refer to GeeksforGeeks
```

本文由 [**潘卡吉·库马尔**](https://in.linkedin.com/in/prakuj) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。