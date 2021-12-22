# Java 中的文件 isAbsolute()方法，带示例

> 原文:[https://www . geesforgeks . org/file-isabsolut-method-in-Java-with-examples/](https://www.geeksforgeeks.org/file-isabsolute-method-in-java-with-examples/)

**isabsolut()**方法是[文件](https://www.geeksforgeeks.org/File-class-in-java/)类的一部分。该函数返回抽象路径名是否为绝对路径名。

**例如:**如果我们使用路径“program.txt”创建一个文件对象，它将指向保存可执行程序的同一目录中的文件(如果您使用的是 IDE，它将指向您保存程序的文件)。这里上面提到的文件路径是“program.txt”，但是这个路径不是绝对的(即不完整)。绝对路径是从根目录开始的完整路径。

**功能签名:**

```
public boolean isAbsolute()
```

**函数语法:**

```
file.isAbsolute()
```

**参数:**此功能不接受任何参数。

**返回值:**该函数返回一个布尔值，该值告诉抽象路径名是否是绝对的。

下面的程序将说明 isAbsolute()函数的使用

**例 1:** 给我们一个文件的文件对象，我们要检查它是不是绝对的

```
// Java program to demonstrate the
// use of isAbsolute() function

import java.io.*;

public class solution {
    public static void main(String args[])
    {
        // try-catch block to handle exceptions
        try {

            // Create a file object
            File f = new File("c:\\users\\program.txt");

            // Check if the given path
            // is absolute or not
            if (f.isAbsolute()) {

                // Display that the path is absolute
                // as the function returned true
                System.out.println("The path is absolute");
            }
            else {

                // Display that the path is not absolute
                // as the function returned false
                System.out.println("The path is not absolute");
            }
        }
        catch (Exception e) {
            System.err.println(e.getMessage());
        }
    }
}
```

**输出:**

```
The path is absolute

```

**例 2:** 给我们一个文件的文件对象，我们要检查它是不是绝对的

```
// Java program to demonstrate the
// use of isAbsolute() function

import java.io.*;

public class solution {
    public static void main(String args[])
    {
        // try-catch block to handle exceptions
        try {

            // Create a file object
            File f = new File("program.txt");

            // Check if the given path
            // is absolute or not
            if (f.isAbsolute()) {

                // Display that the path is absolute
                // as the function returned true
                System.out.println("The path is absolute");
            }
            else {

                // Display that the path is not absolute
                // as the function returned false
                System.out.println("The path is not absolute");
            }
        }
        catch (Exception e) {
            System.err.println(e.getMessage());
        }
    }
}
```

**输出:**

```
The path is not absolute

```

**程序可能无法在在线 IDE 中运行。请使用离线 IDE 并设置文件的父文件**