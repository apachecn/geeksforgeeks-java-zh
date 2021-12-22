# Java 中的文件列表文件()方法，示例

> 原文:[https://www . geesforgeks . org/file-listfiles-method-in-Java-with-examples/](https://www.geeksforgeeks.org/file-listfiles-method-in-java-with-examples/)

**listFiles()** 方法是[文件](https://www.geeksforgeeks.org/File-class-in-java/)类的一部分。函数返回一个文件数组，表示给定抽象路径名中的文件，如果路径名是目录，则返回空值。该函数是一个重载函数。其中一个函数没有任何参数，第二个函数以 FilenameFilter 对象为参数，第三个函数以 filename filter 对象为参数

**功能签名:**

```java
public File[] listFiles()
public File[] listFiles(FilenameFilter f)
public File[] listFiles(FileFilter f)
```

**函数语法:**

```java
file.listFiles()
file.listFiles(filter)
```

**参数:**该函数是一个重载函数

*   其中一个函数没有任何参数，
*   第二个函数将 FilenameFilter 对象作为参数，
*   第三个函数将 FileFilter 对象作为参数

**返回值:**函数返回一个文件数组，如果文件对象是文件，则返回空值。

**异常:**如果不允许函数读取文件，该方法抛出**安全异常**

下面的程序将说明 listFiles()函数的用法

**示例 1:** 我们将尝试查找给定目录

```java
// Java program to demonstrate the
// use of listFiles() function

import java.io.*;

public class solution {
    public static void main(String args[])
    {

        // try-catch block to handle exceptions
        try {

            // Create a file object
            File f = new File("f:\\program");

            // Get all the names of the files present
            // in the given directory
            File[] files = f.listFiles();

            System.out.println("Files are:");

            // Display the names of the files
            for (int i = 0; i < files.length; i++) {
                System.out.println(files[i].getName());
            }
        }
        catch (Exception e) {
            System.err.println(e.getMessage());
        }
    }
}
```

中的所有文件和目录

**输出:**

```java
Files are:
1232.txt
1245.txt
5671.txt
program1

```

**示例 2:** 我们将尝试查找给定目录中所有以“12”

```java
// Java program to demonstrate the
// use of listFiles() function

import java.io.*;

public class solution {
    public static void main(String args[])
    {

        // try-catch block to handle exceptions
        try {

            // Create a file object
            File f = new File("f:\\program");

            // Create a FilenameFilter
            FilenameFilter filter = new FilenameFilter() {

                public boolean accept(File f, String name)
                {
                    return name.startsWith("12");
                }
            };

            // Get all the names of the files present
            // in the given directory
            // and whose names start with "12"
            File[] files = f.listFiles(filter);

            System.out.println("Files are:");

            // Display the names of the files
            for (int i = 0; i < files.length; i++) {
                System.out.println(files[i].getName());
            }
        }
        catch (Exception e) {
            System.err.println(e.getMessage());
        }
    }
}
```

开头的文件和目录

**输出:**

```java
Files are:
1232.txt
1245.txt

```

**示例 3:** 我们将尝试查找给定目录中的所有文件和目录，它们是文本文件

```java
// Java program to demonstrate the
// use of listFiles() function

import java.io.*;

public class solution {
    public static void main(String args[])
    {

        // try-catch block to handle exceptions
        try {

            // Create a file object
            File f = new File("f:\\program");

            // Create a FileFilter
            FileFilter filter = new FileFilter() {

                public boolean accept(File f)
                {
                    return f.getName().endsWith("txt");
                }
            };

            // Get all the names of the files present
            // in the given directory
            // which are text files
            File[] files = f.listFiles(filter);

            System.out.println("Files are:");

            // Display the names of the files
            for (int i = 0; i < files.length; i++) {
                System.out.println(files[i].getName());
            }
        }
        catch (Exception e) {
            System.err.println(e.getMessage());
        }
    }
}
```

**输出:**

```java
Files are:
1232.txt
1245.txt
5671.txt

```

**程序可能无法在在线 IDE 中运行。请使用离线 IDE 并设置文件的父文件**