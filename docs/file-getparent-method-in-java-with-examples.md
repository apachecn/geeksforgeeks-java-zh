# 用 Java 文件 getParent()方法，示例

> 原文:[https://www . geesforgeks . org/file-getparent-method-in-Java-with-examples/](https://www.geeksforgeeks.org/file-getparent-method-in-java-with-examples/)

**getParent()** 方法是[文件](https://www.geeksforgeeks.org/File-class-in-java/)类的一部分。该函数返回给定文件对象的父对象。该函数返回一个包含给定文件对象的父对象的字符串对象。如果抽象路径不包含任何父路径，则返回空字符串。

**功能签名:**

```
public String getParent()
```

**函数语法:**

```
file.getParent()
```

**参数:**此功能不接受任何参数。

**返回值:**函数返回一个字符串值，它是给定文件对象的父对象。

以下程序将说明 getParent()函数的使用:

**例 1:** 给我们一个文件的文件对象，我们要得到文件对象的 Parent。

```
// Java program to demonstrate the
// use of getParent() function

import java.io.*;

public class solution {
    public static void main(String args[])
    {

        // try-catch block to handle exceptions
        try {

            // Create a file object
            File f
                = new File("c:\\users\\program.txt");

            // Get the Parent
            // of the given file f
            String Parent = f.getParent();

            // Display the file Parent
            // of the file object
            System.out.println("File Parent : "
                               + Parent);
        }
        catch (Exception e) {
            System.err.println(e.getMessage());
        }
    }
}
```

**输出:**

```
File Parent : c:\users

```

![](img/113feae8462a70bdd7988a451c6bbea1.png)

**例 2:** 给我们一个目录的文件对象，我们要得到文件对象的 Parent。

```
// Java program to demonstrate the
// use of getParent() function

import java.io.*;

public class solution {
    public static void main(String args[])
    {

        // try-catch block to handle exceptions
        try {

            // Create a file object
            File f
                = new File("c:\\users\\program");

            // Get the Parent
            // of the given file f
            String Parent = f.getParent();

            // Display the file Parent
            // of the file object
            System.out.println("File Parent : "
                               + Parent);
        }
        catch (Exception e) {
            System.err.println(e.getMessage());
        }
    }
}
```

**输出:**

```
File Parent : c:\users

```

![](img/113feae8462a70bdd7988a451c6bbea1.png)

**程序可能无法在在线 IDE 中运行。请使用离线 IDE 并设置文件的父级**