# Java 中 FileInputStream 和 FileReader 的区别

> 原文:[https://www . geesforgeks . org/file inputstream-and-file reader-in-Java/](https://www.geeksforgeeks.org/difference-between-fileinputstream-and-filereader-in-java/)之间的区别

让我们首先讨论它们，以便通过一个例子来理解差异。首先，我们将讨论文件阅读器类。所以从[开始，java 中的 FileReader 类](https://www.geeksforgeeks.org/file-handling-java-using-filewriter-filereader/)用于从文件中读取数据。它以字节格式返回数据，如[文件输入流类](https://www.geeksforgeeks.org/java-io-fileinputstream-class-java/)。这是一个面向字符的类，用于 java 中的文件处理。这个类继承了[输入流阅读器类](https://www.geeksforgeeks.org/inputstreamreader-class-in-java/)。文件阅读器用于读取字符流。

**语法:**

使用文件名创建

```java
FileReader input = new FileReader(String name);
```

使用文件的对象创建

```java
FileReader input = new FileReader(File fileObj);
```

**实施:**

让我们考虑一个示例文件，在该文件中，我们使用 Java FileReader 类从文本文件 Gfg.txt 中读取数据。我们假设文件中有以下数据，即“Gfg.txt”文件，如下所示:

```java
Welcome to GeeksForGeeks.
```

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Illustrate FileReader class

// Importing class
import java.io.FileReader;

// Main class
// FileReaderExample
public class GFG {

    // Main driver method
    public static void main(String args[]) throws Exception
    {

        // Creating an object of FileReader class to
        // read content from file in local directory
        FileReader fr = new FileReader("C:\\Gfg.txt");

        int i;

        // Reads from the file
        while ((i = fr.read()) != -1) {

            // Printing  the content inside the file
            System.out.print((char)i);
        }

        // Closing the connections to
        // avoid memory space
        fr.close();
    }
}
```

**输出:**

```java
Welcome to GeeksForGeeks
```

现在讨论第二种方法，即通过文件输入流类。它存在于同一个包中，即从文件中检索字节的 java.io。它用于读取面向字节的数据(原始字节流)，如图像数据、音频和视频。您也可以从字符流中读取数据。但是，建议使用文件阅读器类来读取字符流。

**语法:**

使用文件路径创建

```java
FileInputStream input = new FileInputStream(stringPath);
```

使用文件的对象创建

```java
FileInputStream input = new FileInputStream(File fileObject);
```

> **注意:**在运行代码之前，需要创建一个名为“Gfg.txt”的文本文件。在这个文件中，我们有以下内容:“欢迎来到极客博客”

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Illustrate FileInputStream class

// Importing class from java.io package
import java.io.FileInputStream;

// Main class
public class GFG {

    // Main driver method
    public static void main(String args[])
    {

        // Try block to check for exceptions
        try {

            // Creating an object of FileInputStream class
            // in main() body to get file
            FileInputStream input
                = new FileInputStream("Gfg.txt");

            // Display message only
            System.out.println("Data in the file: ");

            // Reading the first byte
            int i = input.read();

            while (i != -1) {
                System.out.print((char)i);

                // Reads next byte from the file using
                // next() method
                i = input.read();
            }

            // Closing the file
            input.close();
        }

        // Catch block to handle the exceptions
        catch (Exception e) {

            // Print the exception on the console
            System.out.println(e);
        }
    }
}
```

**输出:**

```java
Data in the file:
Welcome to GeeksForGeeks
```

现在，在了解了这两者之后，让我们总结一下它们之间的差异，这些差异在下面以表格的形式描述。

<figure class="table">

| 

文件输入流

 | 

档案管理员

 |
| --- | --- |
| Stream 是一个基于字节的对象，可以读写字节。 | 阅读器是基于字符的，它可以用来读或写字符。 |
| 文件输入流是基于字节的，它可以用来读取字节。 | 文件阅读器是基于字符的，它可以用来读取字符。 |
| 流用于二进制输入/输出 | 阅读器用于字符输入/输出 |
| FileInputStream 用于读取二进制文件。 | FileReader 用于读取平台默认编码的文本文件。 |
| 序列化和反序列化可以用 FileInputStream 和 ObjectInputStream 完成，序列化的对象可以保存到文件中。序列化将对象转换为字节流，反序列化将其转换回对象。 | 文件读取器不用于序列化和反序列化，因为它读取的是字符而不是字节。 |
| 文件输入流是输入流类的后代。 | 文件阅读器从阅读器类扩展而来 |
| *file inputstream 的 read()方法*可以一次读取一个字节，也可以读取字节数组中的多个字节。 | *file reader 的 read()方法*可以一次读取一个字符，也可以将多个字符读入一个数组 |

</figure>