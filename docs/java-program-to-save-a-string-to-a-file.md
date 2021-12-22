# 将字符串保存到文件的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序-保存-字符串-文件/](https://www.geeksforgeeks.org/java-program-to-save-a-string-to-a-file/)

桌面上一个名为“gfg.txt”的演示文件用作机器上的本地目录。在编写程序之前创建一个空文件，并将该文件的特定路径提供给程序。

**方法:**

1.  使用文件类的 *writeString()方法*
2.  使用文件类的 *write()方法*
3.  使用 Filewriter 类的 writer()方法
4.  使用 Bufferedwriter 类的 write()方法
5.  使用 PrintWriter 类的 write()方法

让我们分别讨论每种方法，通过干净的 java 程序实现相同的方法，以便对它们有一个公平的认识。

**方法 1:** [使用*写字符串()方法【文件类的 T4】*](https://www.geeksforgeeks.org/files-class-writestring-method-in-java-with-examples/)

Java 中[文件](https://www.geeksforgeeks.org/file-class-in-java/)类的 **writeString()** 方法用于将内容写入指定文件。 *java.nio.file.Files'* 类有一个*预定义的*WriteString()方法 ，该方法使用 UTF-8 字符集将所有内容写入一个文件。

**语法:**

```java
Files.writeString(path, string, options)
```

**参数:**

*   **路径:**数据类型为路径的文件路径
*   **字符串:**一个指定的字符串，它将以返回类型字符串进入文件。
*   **选项:**在文件中输入字符串的不同选项。比如将字符串附加到文件中，用当前字符串覆盖文件中的所有内容，等等

**返回值:**此方法不返回值。

**程序:**

*   创建文件的实例。
*   使用实例、字符串和字符集调用 Files.writeString()方法。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Save a String to a File
// Using Files.writeString() method

// Importing required classes
import java.io.*;
import java.io.IOException;
import java.nio.charset.StandardCharsets;
import java.nio.file.Files;
import java.nio.file.Path;
import java.nio.file.Paths;

// Main class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Creating an instance of file
        Path path
            = Paths.get("C:\\Users\\HP\\Desktop\\gfg.txt");

        // Custom string as an input
        String str
            = "Geeks for Geeks \nWelcome to computer science portal \nHello Geek";

        // Try block to check for exceptions
        try {
            // Now calling Files.writeString() method
            // with path , content & standard charsets
            Files.writeString(path, str,
                              StandardCharsets.UTF_8);
        }

        // Catch block to handle the exception
        catch (IOException ex) {
            // Print messqage exception occurred as
            // invalid. directory local path is passed
            System.out.print("Invalid Path");
        }
    }
}
```

**输出:**

```java
Geeks for Geeks
Welcome to computer science portal
Hello Geek
```

**方法 2:** 使用 ***编写文件类**的()方法*

**java.nio.file.Files 类有一个预定义的 write()方法，用于将指定的文本写入文件。**

****程序:****

1.  **创建文件的实例。**
2.  **使用 string.getBytes()方法将字符串转换为字节数组。**
3.  **最后调用方法即 Files.write()用文件实例和字节数组。**

****例****

## **Java 语言(一种计算机语言，尤用于创建网站)**

```java
// Java Program to Save a String to a File
// Using Files.write() method

// Importing required classes
import java.io.*;
import java.io.IOException;
import java.nio.file.Files;
import java.nio.file.Path;
import java.nio.file.Paths;

// Main class
public class GFG {
    // Main driver method
    public static void main(String[] args)
    {
        // Creating an instance of file
        Path path
            = Paths.get("C:\\Users\\HP\\Desktop\\gfg.txt");

        // Custom string as an input
        String str
            = "Geeks for Geeks \nWelcome to computer science portal \nHello Geek!";

        // Converting string to byte array
        // using getBytes() method
        byte[] arr = str.getBytes();

        // Try block to check for exceptions
        try {
            // Now calling Files.write() method using path
            // and byte array
            Files.write(path, arr);
        }

        // Catch block to handle the exceptions
        catch (IOException ex) {
            // Print message as exception occurred when
            // invalid path of local machine is passed
            System.out.print("Invalid Path");
        }
    }
}
```

****输出:****

```java
Geeks for Geeks
Welcome to computer science portal
Hello Geek!
```

****方法 3:** [使用 FileWriter 类的 writer()方法](https://www.geeksforgeeks.org/filewriter-class-in-java/)**

**Filewriter 类用于在文件中写入一些数据。这是一种将数据写入文件的简单方法。**

**![](img/02154bac22fdb3d47200a0c3c5c0029f.png)**

****程序:****

*   **创建文件的实例。**
*   **将文件实例传递到 filewriter。**
*   **现在用字符串数据在文件写入器上调用 ***写入器()方法*** 。**
*   **刷新文件资源。**
*   **关闭文件资源。**

****例****

## **Java 语言(一种计算机语言，尤用于创建网站)**

```java
// Java Program to Save a String to a File
// Using FileWriter class

// Importing required classes
import java.io.*;
import java.io.File;
import java.io.FileWriter;
import java.io.IOException;

public class GFG
{
    public static void main(String[] args) throws IOException
    {
        //creating the instance of file
        File path = new File("C:\\Users\\HP\\Desktop\\gfg.txt");

      //passing file instance in filewriter
        FileWriter wr = new FileWriter(path);

        //calling writer.write() method with the string
        wr.write("Geeks for Geeks \nWelcome to computer science portal \nHello Geek!!");

        //flushing the writer
        wr.flush();

        //closing the writer
        wr.close();
    }
}
```

****输出:****

```java
Geeks for Geeks
Welcome to computer science portal
Hello Geek!!
```

****方法 4:** [使用 BufferedWriter 类的 write()方法](https://www.geeksforgeeks.org/io-bufferedwriter-class-methods-java/)**

**BufferedWriter 类基本上为编写实例提供了一个缓冲区。我们可以将其他一些编写器(如 PrintWriter 和 FileWriter)包装到 BufferedWriter 中。BufferedWriter 对于在文件上执行多个写操作非常有效&写多个文件。BufferedWriter 比 Filewriter 效率更高。**

****程序:****

1.  **创建文件的实例。**
2.  **用 filewriter 声明流。**
3.  **用字符串数据对流调用 write()方法。**

****例****

## **Java 语言(一种计算机语言，尤用于创建网站)**

```java
// Java Program to Save a String to a File
// Using Files.write() method

// Importing required classes
import java.io.*;
import java.io.IOException;
import java.nio.file.Files;
import java.nio.file.Path;
import java.nio.file.Paths;

// Main class
public class GFG {
    // Main driver method
    public static void main(String[] args)
    {
        // Creating an instance of file
        Path path
            = Paths.get("C:\\Users\\HP\\Desktop\\gfg.txt");

        // Custom string as an input
        String str
            = "Geeks for Geeks \nWelcome to computer science portal \nHello Geek!";

        // Converting string to byte array
        // using getBytes() method
        byte[] arr = str.getBytes();

        // Try block to check for exceptions
        try {
            // Now calling Files.write() method using path
            // and byte array
            Files.write(path, arr);
        }

        // Catch block to handle the exceptions
        catch (IOException ex) {
            // Print message as exception occurred when
            // invalid path of local machine is passed
            System.out.print("Invalid Path");
        }
    }
}
```

****输出:****

```java
Geeks for Geeks
Welcome to computer science portal
Hello Geek!!!
```

****方法 5:** [使用 PrintWriter 类的 write()方法](https://www.geeksforgeeks.org/java-io-printwriter-class-java-set-1/)**

**PrintWriter 类是 Writer 类的扩展。PrintWriter 类用于使用 write()方法将字符串数据写入文件。**

****程序:****

1.  **创建文件的实例。**
2.  **创建一个 PrintWriter 流，并将文件实例传递给它。**
3.  **用数据调用 write 方法。**
4.  **冲洗小溪。**
5.  **关闭流。**

****例****

## **Java 语言(一种计算机语言，尤用于创建网站)**

```java
// Java Program to Save a String to a File
// Using PrintWriter class

// Importing required classes
import java.io.*;
import java.io.File;
import java.io.FileNotFoundException;
import java.io.PrintWriter;

// Main clas
public class GFG {

    // Main driver method
    public static void main(String[] args)
        throws FileNotFoundException
    {
        // Creating an instance of file
        File path
            = new File("C:\\Users\\HP\\Desktop\\gfg.txt");

        // Declaring the print writer with path
        PrintWriter pw = new PrintWriter(path);

        // Now calling writer() method with string
        pw.write(
            "Geeks for Geeks \nWelcome to computer science portal \nHello Geek!!!!");

        // Flushing the print writer
        pw.flush();

        // Lastly closing the printwriter
        // using the close() method
        pw.close();
    }
}
```

****输出:****

```java
Geeks for Geeks
Welcome to computer science portal
Hello Geek!!!!
```