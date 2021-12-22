# 用 Java 检查服务器上文件的最后修改

> 原文:[https://www . geesforgeks . org/checking-最后一次修改 java 服务器上的文件/](https://www.geeksforgeeks.org/checking-last-modification-of-a-file-on-the-server-in-java/)

在 Java 中，我们有不同的类，如[文件](https://www.google.com/url?client=internal-element-cse&cx=009682134359037907028:tj6eafkv_be&q=https://www.geeksforgeeks.org/file-class-in-java/&sa=U&ved=2ahUKEwjZ1LmtqobtAhWZzDgGHaOSAhQQFjAAegQIAhAC&usg=AOvVaw36rJsv86qebUcl2Z6d9sWI)、[网址](https://www.google.com/url?client=internal-element-cse&cx=009682134359037907028:tj6eafkv_be&q=https://www.geeksforgeeks.org/url-class-java-examples/&sa=U&ved=2ahUKEwiw7Mq3qobtAhXx4jgGHRZ5DNIQFjAAegQIABAC&usg=AOvVaw3PtDN7xG3n3ynpw6Cbvfki)，它提供了读取文件属性的功能，如创建时间、上次访问时间和上次修改时间。

**方法 1(使用基本属性)**

本示例使用 **java.nio.*** 显示文件的元数据和其他文件属性，如创建时间、上次访问时间和上次修改时间。

## 爪哇

```
// Java Program to get last modification time of the file
import java.io.IOException;
import java.net.HttpURLConnection;
import java.nio.file.Files;
import java.nio.file.Path;
import java.nio.file.Paths;
import java.nio.file.attribute.BasicFileAttributes;

public class GFG {
    public static void main(String args[])
    {
        // storing the path of the file in the string
        String fileName = "C:/Users/elavi/Desktop/File.txt";

        // used exception handling in order to catch the
        // exception
        // which may occur if there is no such file is
        // present at specified location
        // or the path of the file provided by the user is
        // incorrect
        try {
            // getting the path of the file
            Path file = Paths.get(fileName);

            // reading the attributes of the file
            BasicFileAttributes attr = Files.readAttributes(
                file, BasicFileAttributes.class);

            // getting the last modification time of the
            // file
            System.out.println(
                "lastModifiedTime of File Is : "
                + attr.lastModifiedTime());
        }
        catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```