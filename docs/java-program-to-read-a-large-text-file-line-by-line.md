# 一行一行读取大文本文件的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序读取大文本文件逐行/](https://www.geeksforgeeks.org/java-program-to-read-a-large-text-file-line-by-line/)

由于我们对这个话题很熟悉，让我们多加强调，找出它们之间的细微差别。在这里，我们应该从本地目录中的一个文件中读取一个文本文件，说它是' gfg.txt '。让文件中的内容如下所示:

```java
Geeks for Geeks.
A computer science portal.
Welcome to this portal.
Hello Geek !!!
```

> 注意:在做任何事情之前，先在系统存储库中创建一个文件来处理我们的程序\编写一个程序，因为我们将通过我们的程序访问同一个目录。

**方法:**

1.  使用扫描仪类
2.  使用 bufferedreader 类

**方法 1:** [使用扫描仪类](https://www.geeksforgeeks.org/scanner-class-in-java/)

Scanner 是 java.util 包中的一个类，用于获取 int、double 等原语类型的输入。和琴弦。这是在 Java 程序中读取输入的最简单的方法，尽管如果您想要一种用于时间受限的场景的输入法，比如在竞争性编程中，效率不是很高。Scanner 类用于逐行读取大文件。扫描仪将其输入分成标记，默认情况下，标记与空白匹配。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Read a Large Text File Line by Line
// Using Scanner class

// Importing required classes
import java.io.*;
import java.io.FileInputStream;
import java.io.FileNotFoundException;
import java.io.InputStream;
import java.nio.charset.StandardCharsets;
import java.util.Scanner;

// Main class
public class GFG {

    // Main driver method
    public static void main(String[] args)
        throws FileNotFoundException
    {

        // Declaring and initializing the string with
        // custom path of a file
        String path = "C:\\Users\\HP\\Desktop\\gfg.txt";

        // Creating an instance of Inputstream
        InputStream is = new FileInputStream(path);

        // Try block to check for exceptions
        try (Scanner sc = new Scanner(
                 is, StandardCharsets.UTF_8.name())) {

            // It holds true till there is single element
            // left in the object with usage of hasNext()
            // method
            while (sc.hasNextLine()) {

                // Printing the content of file
                System.out.println(sc.nextLine());
            }
        }
    }
}
```

**输出:**

```java
Geeks for Geeks.
A computer science portal.
Welcome to this portal.
Hello Geek !!!
```

**方法二:** [使用 BufferedReader 类](https://www.geeksforgeeks.org/java-io-bufferedreader-class-java/)

BufferedReader 用于逐行读取文件。基本上**、** BufferedReader()是用来处理大文件的。BufferedReader 阅读效率很高。

> **注意:**指定 BufferReader 的大小或保持该大小为 BufferReader 的默认大小。BufferReader 的默认大小是 8KB。

**语法:**

```java
BufferedReader in = new BufferedReader(Reader in, int size);
```

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Read a Large Text File Line by Line
// Using BufferedReader class

// Importing required classes
import java.io.*;
import java.io.BufferedReader;
import java.io.FileReader;
import java.io.IOException;

// Main class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Declaring a string and initializing it with
        // path of file present on the system
        String path = "C:\\Users\\HP\\Desktop\\gfg.txt";

        // Try block to check for exceptions
        try (BufferedReader br
             = new BufferedReader(new FileReader(path))) {

            // Declaring a new string
            String str;

            // It holds true till threre is content in file
            while ((str = br.readLine()) != null) {

                // Printing the file data
                System.out.println(br);
            }
        }

        // Catch block to handle the exceptions
        catch (IOException e) {

            // Display pop up message if exceptionn occurs
            System.out.println(
                "Error while reading a file.");
        }
    }
}
```

**输出:**

```java
Geeks for Geeks.
A computer science portal.
Welcome to this portal.
Hello Geek !!!
```