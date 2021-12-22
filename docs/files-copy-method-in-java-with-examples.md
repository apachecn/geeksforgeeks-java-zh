# Java 中的文件复制()方法，示例

> 原文:[https://www . geesforgeks . org/files-copy-method-in-Java-with-examples/](https://www.geeksforgeeks.org/files-copy-method-in-java-with-examples/)

*java.nio.file.Files 类*的 *copy()方法*用于将字节从文件复制到 I/O 流或从 I/O 流复制到文件。输入/输出流是指代表不同类型源(如磁盘文件)的输入源或输出目的地。

**方法:**根据传递的参数类型，Files 类提供了 3 种类型的 copy()方法。

1.  使用*复制(输入流，路径目标，复制选项…选项)*方法
2.  使用*复制(路径源，输出流输出)*方法
3.  使用*复制(路径源、路径目标、复制选项…选项)*方法

**方法 1:** 使用*复制(输入流，路径目标，复制选项…选项)*方法

此方法用于将输入流中的所有字节复制到文件中。

**参数:**

*   in:将复制其数据的输入流
*   目标:将复制数据的文件的路径
*   选项:描述数据复制方式的选项

**返回类型:**复制的字节数

**异常:**

*   IOException:如果在读取或写入时发生错误
*   文件已存在异常:如果目标文件已经存在并且无法替换
*   如果目标文件是一个非空目录，因此无法替换，请执行以下操作
*   不支持操作例外:如果不支持选项描述的复制方式
*   安全性异常:如果对目标文件的写访问被安全管理器拒绝

**实施:**

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Impoerting classes from java.nio package as
// this package is responsible for network linking
import java.io.ByteArrayInputStream;
import java.io.IOException;
import java.io.InputStream;
import java.nio.file.Files;
import java.nio.file.Path;
import java.nio.file.Paths;
import java.nio.file.StandardCopyOption;

// Main Class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Input custom string
        String text = "geeksforgeeks";

        // Path of the file where data is to be copied
        Path path = (Path)Paths.get("/usr", "local", "bin",
                                    "fileIn.txt");

        System.out.println("Path of target file: "
                           + path.toString());

        // Byte stream whose data is to be copied
        InputStream in
            = new ByteArrayInputStream(text.getBytes());

        // Try block to check for exceptions
        try {

            // Printing number of copied bytes
            System.out.println(
                "Number of bytes copied: "
                + Files.copy(
                    in, path,
                    StandardCopyOption.REPLACE_EXISTING));
        }

        // Catch block to handle the exceptions
        catch (IOException e) {

            // Print the line number where exception occured
            e.printStackTrace();
        }
    }
}
```

**输出:**

```java
Path of target file: /usr/local/bin/fileIn.txt
Number of bytes copied: 13
```

**方法 2:** 使用*副本(路径源，输出流输出)*方法

此方法用于将文件中的所有字节复制到输出流中。

**参数:**需要两个即

*   来源:将复制其数据的文件的路径
*   out:复制的数据将被写入的输出流

**返回类型:**复制的字节数

**异常:**

*   IOException:如果在读取或写入时发生错误
*   安全性异常:如果对目标文件的读取访问被安全管理器拒绝

**实施:**

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Impoerting classes from java.nio package as
// this package is responsible for network linking
import java.io.ByteArrayOutputStream;
import java.io.IOException;
import java.io.OutputStream;
import java.nio.file.Files;
import java.nio.file.Path;
import java.nio.file.Paths;

// Main Class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Path of file whose data is to be copied
        Path path = (Path)Paths.get("/usr", "local", "bin",
                                    "fileOut.txt");

        // Getting the path of source file
        System.out.println("Path of source file: "
                           + path.toString());

        // Output stream where data is to written
        OutputStream out = new ByteArrayOutputStream();

        // Try block to check for exceptions
        try {
            // Printing number of copied bytes
            System.out.println("Number of bytes copied: "
                               + Files.copy(path, out));
        }

        // Catch block to handle the exception
        catch (IOException e) {

            // Print the line number where exception occured
            e.printStackTrace();
        }
    }
}
```

**输出:**

```java
Path of source file: /usr/local/bin/fileOut.txt
Number of bytes copied: 13
```

**方法 3:** 使用*复制(路径源、路径目标、复制选项…选项)*方法

此方法用于将文件复制到目标文件。

**参数:**

*   来源:将复制其数据的文件的路径
*   目标:将复制数据的文件的路径
*   选项:描述数据复制方式的选项

**返回类型:**复制数据的文件路径

**异常:**

*   IOException:如果在读取或写入时发生错误
*   文件已存在异常:如果目标文件已经存在并且无法替换
*   如果目标文件是一个非空目录，因此无法替换，请执行以下操作
*   不支持操作例外:如果不支持选项描述的复制方式
*   安全性异常:如果对目标文件的写访问被安全管理器拒绝

**实施:**

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Impoerting classes from java.nio package as
// this package is responsible for network linking
import java.io.IOException;
import java.nio.file.Files;
import java.nio.file.Path;
import java.nio.file.Paths;
import java.nio.file.StandardCopyOption;

// Main Class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Path of file where data is to copied
        Path pathIn = (Path)Paths.get("/usr", "local",
                                      "bin", "fileIn.txt");
        // Path of file whose data is to be copied
        Path pathOut = (Path)Paths.get(
            "/usr", "local", "bin", "fileOut.txt");

        System.out.println("Path of target file: "
                           + pathIn.toString());

        System.out.println("Path of source file: "
                           + pathOut.toString());

        // Try block to check for exceptions
        try {

            // Printing number of bytes copied
            System.out.println(
                "Number of bytes copied: "
                + Files.copy(
                    pathOut, pathIn,
                    StandardCopyOption.REPLACE_EXISTING));
        }

        // Catch block to handle the exceptions
        catch (IOException e) {

            // Print the line number where exception occured
            e.printStackTrace();
        }
    }
}
```

**输出:**

```java
Path of target file: /usr/local/bin/fileIn.txt
Path of source file: /usr/local/bin/fileOut.txt
Number of bytes copied: 13 
```