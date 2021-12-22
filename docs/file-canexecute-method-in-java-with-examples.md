# 用示例将 canExecute()方法用 Java 文件化

> 原文:[https://www . geesforgeks . org/file-canexecute-method-in-Java-with-examples/](https://www.geeksforgeeks.org/file-canexecute-method-in-java-with-examples/)

**canExecute()** 函数是 Java 中[文件](https://www.geeksforgeeks.org/file-class-in-java/)类的一部分。该函数确定程序是否可以执行由抽象路径名表示的指定文件。如果文件路径存在，并且允许应用程序执行该文件，则此方法将返回 true。否则它将返回假的。

**功能签名:**

```
public boolean canExecute()
```

**语法:**

```
file.canExecute();
```

**参数:**此功能不接受任何参数。

**返回值:**该函数返回一个**布尔值**，代表指定文件是否可以执行。

**异常:**如果文件的读访问被拒绝，该方法抛出**安全异常**

下面的程序说明了 canExecute()函数的使用:

**示例 1:** 文件“F:\\program.txt”是 F:目录中的现有文件，程序被允许执行该文件。

```
// Java program to demonstrate
// canExecute() method of File class

import java.io.*;

public class solution {

    // Driver Code
    public static void main(String args[])
    {

        // Get the file to be executed
        File f = new File("F:\\program.txt");

        // Check if this file
        // can be executed or not
        // using canExecute() method
        if (f.canExecute()) {

            // The file is can be executed
            // as true is returned
            System.out.println("Executable");
        }
        else {

            // The file is cannot be executed
            // as false is returned
            System.out.println("Non Executable");
        }
    }
}
```

**输出:**

```
Executable
```

**示例 2:** 文件“F:\ program 1 . txt”不存在我们将尝试检查该文件是否可执行。

```
// Java program to demonstrate
// canExecute() method of File class

import java.io.*;

public class solution {

    // Driver Code
    public static void main(String args[])
    {

        // Get the file to be executed
        File f = new File("F:\\program1.txt");

        // Check if this file
        // can be executed or not
        // using canExecute() method
        if (f.canExecute()) {

            // The file is can be executed
            // as true is returned
            System.out.println("Executable");
        }
        else {

            // The file is cannot be executed
            // as false is returned
            System.out.println("Non Executable");
        }
    }
}
```

**输出:**

```
Non Executable
```

**注意:程序可能无法在在线 IDE 中运行。请使用脱机集成开发环境并设置文件路径。**