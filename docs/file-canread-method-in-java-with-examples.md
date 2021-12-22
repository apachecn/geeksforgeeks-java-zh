# Java 中的文件 canRead()方法，示例

> 原文:[https://www . geesforgeks . org/file-can read-method-in-Java-with-examples/](https://www.geeksforgeeks.org/file-canread-method-in-java-with-examples/)

**canRead()** 函数是 Java 中[文件](https://www.geeksforgeeks.org/file-class-in-java/)类的一部分。该函数确定程序是否可以读取由抽象路径名表示的文件。如果抽象文件路径存在，并且允许应用程序读取该文件，则该函数返回 true。

**功能签名:**

```
public boolean canRead()

```

**语法:**

```
file.canRead()

```

**参数:**此方法不接受任何参数。

**返回值:**该函数返回一个**布尔值**，表示应用程序是否被允许读取文件。

**异常:**如果文件的读访问被拒绝，该方法抛出**安全异常**。

下面程序说明了 canRead()函数的使用:

**例 1:** 文件“F:\ program . txt”可读

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// canRead() method of File Class

import java.io.*;

public class solution {
    public static void main(String args[])
    {

        // Get the file
        File f = new File("F:\\program.txt");

        // Check if the specified file
        // can be read or not
        if (f.canRead())
            System.out.println("Can be Read");
        else
            System.out.println("Cannot be Read");
    }
}
```

**输出:**

```
Can be Read

```

**例 2:** 文件“F:\ program 1 . txt”不可读

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// canRead() method of File Class

import java.io.*;

public class solution {
    public static void main(String args[])
    {

        // Get the file
        File f = new File("F:\\program1.txt");

        // Check if the specified file
        // can be read or not
        if (f.canRead())
            System.out.println("Can be Read");
        else
            System.out.println("Cannot be Read");
    }
}
```

**输出:**

```
Cannot be Read

```

**注意:**程序可能无法在在线 IDE 中运行。请使用脱机集成开发环境并设置文件路径。