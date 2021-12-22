# 将文件转换为字节数组的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序到转换文件到字节数组/](https://www.geeksforgeeks.org/java-program-to-convert-file-to-a-byte-array/)

为了说明机器本地目录中的文本文件到字节数组的转换，我们将考虑一个名为“假设它是本地目录中的‘gfg . txt’”的随机文件。让文件中的内容如下所示:

```java
Geeks for Geeks.
```

> 注意:在做任何事情之前，先在系统存储库中创建一个文件来处理我们的程序\编写一个程序，因为我们将通过我们的程序访问同一个目录。

**方法:**

1.  使用 FileInputStream 类的 read(byte[])方法
2.  使用 Files.readAllBytes()方法

**方法 1:** [使用**读取文件输入流类的(字节[])方法**](https://www.geeksforgeeks.org/java-io-fileinputstream-class-java/)

FileInputStream 对于以字节序列的形式从文件中读取数据非常有用。FileInputStream 用于读取原始字节流，如图像数据。要读取字符流，请考虑使用[文件阅读器](https://www.geeksforgeeks.org/file-handling-java-using-filewriter-filereader/)。*file inputstream 类的 read(byte[])方法*，该方法读取文件的长度，然后将该输入流中的字节数据转换为字节数组。

**程序:**

1.  使用文件路径创建文件输入流的实例。
2.  创建一个长度相同的字节数组。
3.  将文件内容读取到数组中
4.  打印字节数组
5.  关闭文件输入流的实例，因为这是一个很好的做法，以避免运行时遇到任何异常或错误，并释放内存资源，使我们的程序得到优化，从而加快执行速度。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Convert File to a Byte Array
// Using  read(byte[]) method

// Importing required classes
import java.io.*;
import java.io.File;
import java.io.FileInputStream;
import java.io.IOException;
import java.util.Arrays;

// Main class
public class GFG {

    // Method 1
    // To convert file to byte array
    public static byte[] method(File file)
        throws IOException
    {

        // Creating an object of FileInputStream to
        // read from a file
        FileInputStream fl = new FileInputStream(file);

        // Now creating byte array of same length as file
        byte[] arr = new byte[(int)file.length()];

        // Reading file content to byte array
        // using standard read() method
        fl.read(arr);

        // lastly closing an instance of file input stream
        // to avoid memory leakage
        fl.close();

        // Returning above byte array
        return arr;
    }

    // Method 2
    // Main driver method
    public static void main(String[] args)
        throws IOException
    {

        // Creating an object of File class and
        // providing local directory path of a file
        File path
            = new File("C:\\Users\\HP\\Desktop\\gfg.txt");

        // Calling the Method1 in main() to
        // convert file to byte array
        byte[] array = method(path);

        // Printing the byte array
        System.out.print(Arrays.toString(array));
    }
}
```

**输出:**

```java
[71, 101, 101, 107, 115, 32, 102, 111, 114, 32, 71, 101, 101, 107, 115, 46, 10]
```

现在让我们细想一下实现同样目标的另一种方式。

**方法 2:** 使用**file . readall bytes()方法**

java.nio.file.Files 类具有预定义的 readAllBytes()方法，该方法从文件中读取所有字节。

**程序:**

1.  采用文本文件路径
2.  通过调用 Files.readAllBytes()将该文件转换为字节数组。
3.  打印字节数组。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Convert File to a Byte Array
// Using Files.readAllBytes() method

// Importing required classes
import java.io.*;
import java.io.IOException;
import java.nio.file.Files;
import java.nio.file.Path;
import java.nio.file.Paths;
import java.util.Arrays;

// Main class
public class GFG {

    // Main driver method
    public static void main(String[] args)
        throws IOException
    {

        // Creating an object of Path class and
        // assigning local directory path of file to it
        Path path
            = Paths.get("C:\\Users\\HP\\Desktop\\gfg.txt");

        // Now convert  file into a byte array
        // using Files.readAllBytes() method
        byte[] arr = Files.readAllBytes(path);

        // Lastly print the above byte array
        System.out.println(Arrays.toString(arr));
    }
}
```

**输出:**

```java
[71, 101, 101, 107, 115, 32, 102, 111, 114, 32, 71, 101, 101, 107, 115, 46, 10]
```