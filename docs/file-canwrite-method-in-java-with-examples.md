# Java 中的 File canWrite()方法，带示例

> 原文:[https://www . geesforgeks . org/file-can write-method-in-Java-with-examples/](https://www.geeksforgeeks.org/file-canwrite-method-in-java-with-examples/)

**canWrite()** 函数是 Java 中[文件](https://www.geeksforgeeks.org/file-class-in-java/)类的一部分。这个函数决定程序是否可以写由抽象路径名表示的文件。如果抽象文件路径存在，并且允许应用程序写入文件，则函数返回 true。

**功能签名:**

```java
public boolean canWrite()
```

**语法:**

```java
file.canWrite()
```

**参数:**此方法不接受任何参数。

**返回值:**该函数返回**布尔值**，表示应用程序是否被允许写入文件。

**异常:**如果文件的写访问被拒绝，该方法抛出**安全异常**

下面程序说明了 canWrite()函数的使用:

**例 1:** 文件“F:\ program . txt”可写

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// canWrite() method of File Class

import java.io.*;

public class solution {
    public static void main(String args[])
    {

        // Get the file
        File f = new File("F:\\program.txt");

        // Check if the specified file
        // can be written or not
        if (f.canWrite())
            System.out.println("Can be written");
        else
            System.out.println("Cannot be written");
    }
}
```

**Output:**

```java
Can be written
```

**例 2:** 文件“F:\ program 1 . txt”可写

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// canWrite() method of File Class

import java.io.*;

public class solution {
    public static void main(String args[])
    {

        // Get the file
        File f = new File("F:\\program1.txt");

        // Check if the specified file
        // can be written or not
        if (f.canWrite())
            System.out.println("Can be written");
        else
            System.out.println("Cannot be written");
    }
}
```

**Output:**

```java
Cannot be written
```

**注意:程序可能无法在在线 IDE 中运行。请使用脱机集成开发环境并设置文件路径。**