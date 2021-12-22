# 将文件读入字符串的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序到读取文件到字符串/](https://www.geeksforgeeks.org/java-program-to-read-a-file-to-string/)

有多种方法可以读写文本文件。在处理许多应用程序时，这是必需的。有几种方法可以读取 Java 中的纯文本文件，例如，您可以使用[文件阅读器](https://www.geeksforgeeks.org/file-handling-java-using-filewriter-filereader/)、[buffere reader](https://www.geeksforgeeks.org/java-io-bufferedreader-class-java/)或[扫描仪](https://www.geeksforgeeks.org/scanner-class-in-java/)来读取文本文件。

给定一个文本文件，任务是读取本地目录中的文件内容，并将其存储在字符串中。考虑系统上存在的一个文件，也就是说它是' gfg.txt '。让文件中的随机内容如下所示插入到 pretag 块中。现在我们将讨论实现相同目标的各种方法。文件“gfg.txt”中的内容如图示块所示。

**图示:**文件内的行

```java
Geeks-for-Geeks
A computer science portal
World's largest technical hub
```

> **注意:**用将上述文本文件保存到本地计算机。并在程序中使用该路径。

**方法:**

有几种方法可以实现这个目标，随着 java 版本的进步，有一些特定的方法被提出来，并按顺序进行讨论。

**方法:**

1.  使用 File.readString()方法
2.  使用 BufferReader 类的 readLine()方法
3.  使用 File.readAllBytes()方法
4.  使用 File.lines()方法
5.  使用扫描仪类

让我们通过实现干净的 java 程序来讨论它们，以便理解它们。

**方法 1:** [使用 File.readString()方法](https://www.geeksforgeeks.org/files-class-readstring-method-in-java-with-examples/)

Java 中[文件](https://www.geeksforgeeks.org/file-class-in-java/)类的 **readString()** 方法用于将内容读取到指定的文件中。

**语法:**

```java
Files.readString(filePath) ;
```

**参数:**数据类型为路径的文件路径

**返回值:**该方法以字符串格式返回文件内容。

> **注意:** File.readString()方法是在 Java 11 中引入的，该方法用于将文件的内容读入 String。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program Illustrating Reading a File to a String
// Using Using File.readString() method

// Importing required classes
import java.io.*;
import java.io.IOException;
import java.nio.file.Files;
import java.nio.file.Path;

// Main class
public class GFG {

    // Main driver method
    public static void main(String[] args)
        throws IOException
    {

        // Creating a path choosing file from local
        // directory by creating an object of Path class
        Path fileName
            = Path.of("C:\\Users\\HP\\Desktop\\gfg.txt");

        // Now calling Files.readString() method to
        // read the file
        String str = Files.readString(fileName);

        // Printing the string
        System.out.println(str);
    }
}
```

**输出:**

```java
Geeks-for-Geeks
A computer science portal
World's largest technical hub
```

**方法 2:** [使用 BufferReader 类的 readLine()方法](https://www.geeksforgeeks.org/bufferedreader-readline-method-in-java-with-examples/)

BufferedReader 是一个用于从字符输入流中读取文本的对象。BufferReader 方法中的 *readLine()方法*用于一次读取一行文件并返回内容。

**语法:**

```java
public String readLine() 
throws IOException
```

**参数:**此方法不接受任何参数。

**返回值:**该方法返回由该方法读取的字符串，并排除任何可用的终止符号。如果缓冲流已经结束，并且没有要读取的行，则该方法返回空值。

**异常:**如果出现输入输出错误，此方法将抛出异常。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program Illustrating Reading a File to a String
// Using readLine() method of BufferReader class

// Importing required classes
import java.io.*;
import java.io.BufferedReader;
import java.io.FileReader;
import java.io.IOException;

// MAin class
public class GFG {

    // Method 1
    // To read file content into the string
    // using BufferedReader and FileReader
    private static String method(String filePath)
    {

        // Declaring object of StringBuilder class
        StringBuilder builder = new StringBuilder();

        // try block to check for exceptions where
        // object of BufferedReader class us created
        // to read filepath
        try (BufferedReader buffer = new BufferedReader(
                 new FileReader(filePath))) {

            String str;

            // Condition check via buffer.readLine() method
            // holding true upto that the while loop runs
            while ((str = buffer.readLine()) != null) {

                builder.append(str).append("\n");
            }
        }

        // Catch block to handle the exceptions
        catch (IOException e) {

            // Print the line number here exception occured
            // using printStackTrace() method
            e.printStackTrace();
        }

        // Returning a string
        return builder.toString();
    }

    // Method 2
    // Main driver method
    public static void main(String[] args)
    {

        // Custom input file path stored in string type
        String filePath = "C:\\Users\\HP\\Desktop\\gfg.txt";

        // Calling the Method 1 to
        // read file to a string
        System.out.println(method(filePath));
    }
}
```

**输出:**

```java
Geeks-for-Geeks
A computer science portal
World's largest technical hub
```

**方法 3:** [使用 File.readAllBytes()方法](https://www.geeksforgeeks.org/file-readallbytes-method-in-csharp-with-examples/)

File.readAllBytes()方法用于读取文件中的所有字节。方法确保在读取所有字节或引发输入/输出错误或其他运行时异常时关闭文件。读取所有字节后，我们将这些字节传递给字符串类构造函数来创建一个字符串。

**语法:**

```java
public static byte[] ReadAllBytes (string path);
```

**参数:**打开读取的指定文件路径。

**进场:**

*   声明空字符串
*   Path 类的 ***get()方法*** 通过将作为参数传递给文件来帮助获取文件。
*   现在 File 类的 ***readAllBytes()方法*** 通过传入来读取上面的文件。
*   最后，打印字符串。

**异常:**

*   ArgumentException:*路径*是零长度字符串，只包含空格，或者一个或多个由 InvalidPathChars 定义的无效字符。
*   ArgumentNullException:*路径*为空。
*   路径工具异常:指定的*路径*，文件名或两者都超过了系统定义的最大长度。
*   DirectoryNotFoundException:指定的*路径*无效。
*   IOException:打开文件时出现输入/输出错误。
*   未授权访问异常:当前平台不支持此操作。或者*路径*指定了一个目录。或者呼叫者没有所需的权限。
*   文件未找到异常:在*路径*中指定的文件未找到。
*   NotSupportedException:*路径*的格式无效。
*   安全性异常:调用方没有所需的权限。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program Illustrating Reading a File to a String
// Using File.readAllBytes() method

// Importing required classes
import java.io.*;
import java.io.IOException;
import java.nio.file.Files;
import java.nio.file.Paths;

// Main class
public class GFG {

    // Method 1
    // To read the file content into string with
    // Files.readAllBytes(Path path)
    private static String method(String file_path)
    {

        // Declaring an empty string
        String str = "";

        // Try block to check for exceptions
        try {

            // Reading all bytes form file and
            // storing that in the string
            str = new String(
                Files.readAllBytes(Paths.get(file_path)));
        }

        // Catch block to handle the exceptions
        catch (IOException e) {

            // Print the exception along with line number
            // using printStackTrace() method
            e.printStackTrace();
        }

        return str;
    }

    // Method 2
    // Main driver method
    public static void main(String[] args)
    {

        // Path is passed from local directory of machine
        // and stored in a string
        String filePath = "C:\\Users\\HP\\Desktop\\gfg.txt";

        // Now call Method1 to
        // read the content in above directory
        System.out.println(method(filePath));
    }
}
```

**输出:**

```java
Geeks-for-Geeks
A computer science portal
World's largest technical hub
```

**方法 4:** *使用 File.lines()方法*

File.lines()方法用于将文件中的所有行读取到流中。然后使用指定的字符集(如 UTF 8)将文件中的字节解码成字符。

**语法:**

```java
public static Stream<String> lines(Path path, Charset cs)
throws IOException
```

**参数:**一般有两个参数:

*   用于解码的字符集。
*   文件的路径。

**返回类型:**文件中的行作为字符串。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program Illustrating Reading a File to a String
// Using File.lines() method

// Importing required classes
import java.io.*;
import java.io.IOException;
import java.nio.charset.StandardCharsets;
import java.nio.file.Files;
import java.nio.file.Paths;
import java.util.stream.Stream;

// Main class
public class GFG {

    // Method 1
    // To read the file content into the string with -
    // Files.lines()
    private static String method(String filePath)
    {

        // Declaring an object of StringBuilder class
        StringBuilder contentBuilder = new StringBuilder();

        // try block to check for exceptions

        // Reading file to string using File.lines() method
        // and storing it in an object of Stream class
        try (Stream<String> stream
             = Files.lines(Paths.get(filePath),
                           StandardCharsets.UTF_8)) {
            stream.forEach(
                s -> contentBuilder.append(s).append("\n"));
        }

        // Catch block to handle the exceptions
        catch (IOException e) {

            // Print the line number where exception occured
            // using printStackTrace() method
            e.printStackTrace();
        }

        // Returning the string builder by
        // calling tostring() method
        return contentBuilder.toString();
    }

    // Method 2
    // Main driver method
    public static void main(String[] args)
    {

        // Custom file path is stored as as string
        String filePath = "C:\\Users\\HP\\Desktop\\gfg.txt";

        // Calling method 1 to read content of a file
        System.out.println(method(filePath));
    }
}
```

**输出:**

```java
Geeks-for-Geeks
A computer science portal
World's largest technical hub
```

**方法 5:** [使用 Scanner 类](https://www.geeksforgeeks.org/scanner-hasnextint-method-in-java-with-examples/)的 next()和 hasNext()方法

Scanner 类通过将输入分解成从输入流中顺序检索的标记来工作。Scanner 类有两个名为 next()和 hasNext()的内置方法。这两种内置方法都返回字符串类型的对象。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program Illustrating Reading a File to a String
// Using next() and hasNext() method of Scanner class

// Importing required classes
import java.io.*;
import java.io.IOException;
import java.nio.file.Path;
import java.util.Scanner;

// Main class
public class GFG {

    // Main driver method
    public static void main(String[] args)
        throws IOException
    {

        // Creating object of Path class where custom local
        // directory path is passed as arguments using .of()
        // method
        Path fileName
            = Path.of("C:\\Users\\HP\\Desktop\\gfg.txt");

        // Creating an object of Scanner class
        Scanner sc = new Scanner(fileName);

        // It holds true till there is single element left
        // via hasNext() method
        while (sc.hasNext()) {
            // Iterating over elements in object
            System.out.println(sc.next());
        }

        // Closing scanner class object to avoid errors and
        //  free up memory space
        sc.close();
    }
}
```

**输出:**

```java
Geeks-for-Geeks
A computer science portal
World's largest technical hub
```