# 获取文件创建时间的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-program-to-get-creation-time-of-a-file/](https://www.geeksforgeeks.org/java-program-to-get-the-creation-time-of-a-file/)

使用 [java.nio 包](https://www.geeksforgeeks.org/introduction-to-java-nio-with-examples/)通过 java 提取任意文件的创建日期和时间。要提取文件的日期和时间，请使用 BasicFileAttributes 类。java.nio package 帮助我们获得创建时间、最后访问时间和最后修改时间，它对文件和目录都有效。

**方法:**

1.  Import the necessary java libraries.
2.  The path of the file where we want to store the creation time.
3.  Create a path object and specify the path of the file in it.
4.  Then we must use the readAttributes () method to create the BasicFileAttributes class.
5.  In the readAttributes () method, we must pass two parameters, namely the path object and the BasicFileAttributes class.
6.  Now we only need to call the creationTime () method with the property.

下面是实现获取文件的创建时间:

## 【Java】

```java
// Java program to get the creation time of a file
import java.io.File;
import java.io.IOException;
import java.nio.file.Files;
import java.nio.file.Path;
import java.nio.file.attribute.BasicFileAttributes;

public class JavafileCreationTime {

    public static void main() throws IOException
    {
        // storing the path of the file in the variable
        String filename
            = "C:/Users/HARDSOL/Desktop/New folder (2)";

        // creating the File class object
        File my_file = new File(filename);

        // creating the path object
        Path path = my_file.toPath();

        // creating BasicFileAttributes class object using
        // readAttributes method
        BasicFileAttributes file_att = Files.readAttributes(
            path, BasicFileAttributes.class);

        // printing the file creation time by calling
        // creationTime() method
        System.out.printf("File Creation Time %s%n ",
                          file_att.creationTime());
    }
}
```