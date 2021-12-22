# Java 中的 File exists()方法，示例

> 原文:[https://www . geesforgeks . org/file-exists-method-in-Java-with-examples/](https://www.geeksforgeeks.org/file-exists-method-in-java-with-examples/)

**exists()** 函数是 Java 中[文件](https://www.geeksforgeeks.org/file-class-in-java/)类的一部分。此函数确定是否存在由抽象文件名表示的文件或目录。如果抽象文件路径存在，函数返回 true，否则返回 false。

**语法:**

```
public boolean exists()
```

```
file.exists()
```

**参数:**此方法不接受任何参数。

**返回值:**如果抽象文件名表示的文件存在或不存在，该函数返回**布尔值**。

**异常:**如果文件的写访问被拒绝，该方法抛出**安全异常**

**实现:**考虑如下提供本地目录的系统上的本地目录上的文件。

> " F:\ program . txt "

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Illustrate exists() method of File Class

// Importing input output classes
import java.io.*;

// Main class
public class GFG {

    // Main driver method
    public static void main(String args[])
    {
        // Getting the file by creating object of File class
        File f = new File("F:\\program.txt");

        // Checking if the specified file exists or not
        if (f.exists())

            // Show if the file exists
            System.out.println("Exists");
        else

            // Show if the file does not exists
            System.out.println("Does not Exists");
    }
}
```

**输出:**

```
Exists
```

> 现在让我们考虑文件可写的用例

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// exists() method of File Class

// Importing input output classes
import java.io.*;

// Main class
public class GFG {

    // Main driver method
    public static void main(String args[])
    {
        // Getting the file
        File f = new File("F:\\program1.txt");

        // Checking if the specified file
        // exists or not
        if (f.exists())

            // Print message if it exists
            System.out.println("Exists");
        else

            // Print message if it does not exists
            System.out.println("Does not Exists");
    }
}
```

**输出:**

```
Does not Exists
```