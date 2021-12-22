# Java 中的 File getPath()方法，带示例

> 原文:[https://www . geesforgeks . org/file-get path-method-in-Java-with-examples/](https://www.geeksforgeeks.org/file-getpath-method-in-java-with-examples/)

**getPath()** 方法是[文件](https://www.geeksforgeeks.org/File-class-in-java/)类的一部分。这个函数返回给定文件对象的路径。该函数返回一个包含给定文件对象路径的字符串对象。

**功能签名:**

```
public String getPath()
```

**函数语法:**

```
file.getPath()
```

**参数:**此功能不接受任何参数。

**返回值:**该函数返回一个字符串值，该值是给定文件对象的路径。

下面的程序将说明 getPath()函数的使用:

**例 1:** 给我们一个文件的文件对象，我们要得到文件对象的路径。

```
// Java program to demonstrate the
// use of getPath() function

import java.io.*;

public class solution {
    public static void main(String args[])
    {

        // try catch block to handle exceptions
        try {

            // Create a file object
            File f
                = new File("c:\\users\\program.txt");

            // Get the path of the given file f
            String path = f.getPath();

            // Display the file path of the file object
            System.out.println("File path : " + path);
        }
        catch (Exception e) {
            System.err.println(e.getMessage());
        }
    }
}
```

**输出:**

```
File path : c:\users\program.txt

```

![](img/d3e073a723d8bad2aa282a3414ea2d77.png)

**例 2:** 给我们一个目录的文件对象，我们要得到文件对象的路径。

```
// Java program to demonstrate the
// use of getPath() function

import java.io.*;

public class solution {
    public static void main(String args[])
    {

        // try catch block to handle exceptions
        try {

            // Create a file object
            File f = new File("c:\\users\\program");

            // Get the path of the given file f
            String path = f.getPath();

            // Display the file path of the file object
            System.out.println("File path : " + path);
        }
        catch (Exception e) {
            System.err.println(e.getMessage());
        }
    }
}
```

**输出:**

```
File path : c:\users\program

```

![](img/3b2f348a06b88ad2be1086770ab39570.png)

**程序可能无法在在线 IDE 中运行。请使用离线 IDE 并设置文件的路径**