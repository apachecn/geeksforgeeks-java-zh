# Java 中的文件列表()方法，示例

> 原文:[https://www . geesforgeks . org/file-list-method-in-Java-with-examples/](https://www.geeksforgeeks.org/file-list-method-in-java-with-examples/)

**列表()**方法是[文件](https://www.geeksforgeeks.org/File-class-in-java/)类的一部分。函数返回一个字符串数组，表示给定抽象路径名中的文件，如果路径名是目录，则返回 null。该函数是一个重载函数。其中一个函数没有任何参数，另一个函数以 FilenameFilter 对象为参数

**功能签名:**

```
public String[] list()
public String[] list(FilenameFilter f)
```

**函数语法:**

```
file.list()
file.list(filter)
```

**参数:**该函数是一个重载函数。其中一个函数没有任何参数，另一个函数以**文件名过滤器对象**为参数

**返回值:**函数返回字符串数组，如果文件对象是文件，则返回空值。

**异常:**如果不允许函数对文件进行写访问，该方法抛出**安全异常**。

下面的程序将说明 list()函数的用法

**示例 1:** 我们将尝试查找给定目录

```
// Java program to demonstrate the
// use of list() function

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
            String[] files = f.list();

            System.out.println("Files are:");

            // Display the names of the files
            for (int i = 0; i < files.length; i++) {
                System.out.println(files[i]);
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

```
Files are:
1232.txt
1245.txt
5671.txt
program1

```

**示例 2:** 我们将尝试查找给定目录中所有以“12”

```
// Java program to demonstrate the
// use of list() function

import java.io.*;

public class solution {
    public static void main(String atry-catch  {

        // try catch block to handle exceptions
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
            String[] files = f.list(filter);

            System.out.println("Files are:");

            // Display the names of the files
            for (int i = 0; i < files.length; i++) {
                System.out.println(files[i]);
            }
        }
        catch (Exception e) {
            System.err.println(e.getMessage());
        }
    }
```

开头的文件和目录

**输出:**

```
Files are:
1232.txt
1245.txt

```

**程序可能无法在在线 IDE 中运行。请使用离线 IDE 并设置文件的父文件**