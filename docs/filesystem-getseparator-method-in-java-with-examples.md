# Java 中的文件系统 getSeparator()方法，示例

> 原文:[https://www . geesforgeks . org/file system-get separator-method-in-Java-with-examples/](https://www.geeksforgeeks.org/filesystem-getseparator-method-in-java-with-examples/)

一个**文件系统**类的 **getSeparator()** 方法用于将该文件系统的名称分隔符作为字符串返回。名称分隔符用于分隔路径字符串中的名称。在默认提供程序的情况下，此方法返回与字符串相同的分隔符。
**语法:**

```
public abstract String getSeparator()
```

**参数:**此方法不接受任何内容。
**返回值:**该方法返回与 String 相同的分隔符。
以下程序说明了 getSeparator()方法:
**程序 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// FileSystem.getSeparator() method

import java.nio.file.FileSystem;
import java.nio.file.Path;
import java.nio.file.Paths;

public class GFG {

    public static void main(String[] args)
    {

        // create the object of Path
        Path path
            = Paths.get(
                "C:\\Movies\\document.txt");

        // get FileSystem object
        FileSystem fs = path.getFileSystem();

        // apply getSeparator() methods
        String separator = fs.getSeparator();

        // print
        System.out.println("Separator: "
                           + separator);
    }
}
```

**输出:**

![](img/6e64350e1a73ce695927b98108fca5ed.png)

**节目 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// FileSystem.getSeparator() method

import java.nio.file.FileSystem;
import java.nio.file.Path;
import java.nio.file.Paths;

public class GFG {

    public static void main(String[] args)
    {

        // create the object of Path
        Path path
            = Paths.get(
                "E:// Tutorials// file.txt");

        // get FileSystem object
        FileSystem fs = path.getFileSystem();

        // apply getSeparator() methods
        String separator = fs.getSeparator();

        // print
        System.out.println("File Separator: "
                           + separator);
    }
}
```

**Output:** 

参考资料:[https://docs . Oracle . com/javase/10/docs/API/Java/nio/file/file . html # getSeparator()](https://docs.oracle.com/javase/10/docs/api/java/nio/file/FileSystem.html#getSeparator())