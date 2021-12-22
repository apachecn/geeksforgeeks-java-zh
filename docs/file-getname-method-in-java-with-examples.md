# Java 中的 File getName()方法，带示例

> 原文:[https://www . geesforgeks . org/file-getname-method-in-Java-with-examples/](https://www.geeksforgeeks.org/file-getname-method-in-java-with-examples/)

**getName()** 方法是[文件](https://www.geeksforgeeks.org/File-class-in-java/)类的一部分。该函数返回给定文件对象的名称。该函数返回一个包含给定文件对象名称的字符串对象。如果抽象路径不包含任何名称，则返回空字符串。

**功能签名:**

```java
public String getName()
```

**函数语法:**

```java
file.getName()
```

**参数:**此功能不接受任何参数。

**返回值:**这个函数返回一个字符串值，它是给定文件对象的名称。

下面的程序将说明 getName()函数的用法:

**例 1:** 给我们一个文件的文件对象，我们要得到文件对象的名称。

```java
// Java program to demonstrate the
// use of getName() function

import java.io.*;

public class solution {
    public static void main(String args[])
    {

        // try-catch block to handle exceptions
        try {

            // Create a file object
            File f = new File("c:\\users\\program.txt");

            // Get the Name of the given file f
            String Name = f.getName();

            // Display the file Name of the file object
            System.out.println("File Name : " + Name);
        }
        catch (Exception e) {
            System.err.println(e.getMessage());
        }
    }
}
```

**输出:**

```java
File Name : program.txt

```

![](img/76c64e1f25e0624a88b8de936b9fe4f1.png)

**例 2:** 给我们一个目录的文件对象，我们要得到文件对象的名称。

```java
// Java program to demonstrate the
// use of getName() function

import java.io.*;

public class solution {
    public static void main(String args[])
    {
        // try-catch block to handle exceptions
        try {

            // Create a file object
            File f
                = new File("c:\\users\\program");

            // Get the Name of the given file f
            String Name = f.getName();

            // Display the file Name
            // of the file object
            System.out.println("File Name : "
                               + Name);
        }
        catch (Exception e) {
            System.err.println(e.getMessage());
        }
    }
}
```

**输出:**

```java
File Name :program

```

![](img/b94948f56081203b633c04c379225e78.png)

**程序可能无法在在线 IDE 中运行。请使用离线 IDE 并设置文件名称**