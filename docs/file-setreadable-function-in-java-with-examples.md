# Java 中的文件集可读()函数，示例

> 原文:[https://www . geesforgeks . org/file-set readable-function-in-Java-with-examples/](https://www.geeksforgeeks.org/file-setreadable-function-in-java-with-examples/)

**setReadable()** 方法是[文件](https://www.geeksforgeeks.org/File-class-in-java/)类的一部分。该函数设置所有者或每个人读取抽象路径名的权限。
函数是重载函数一个函数需要两个参数，另一个只需要一个。

**功能签名:**

```
public boolean setReadable(boolean a, boolean b)
public boolean setReadable(boolean a)
```

**函数语法:**

```
file.setReadable(boolean a, boolean b)
file.setReadable(boolean a)
```

**参数:**该函数是一个重载函数:

*   **For the first overload:**
    *   如果真值作为第一个参数传递，则允许它读取抽象路径名，否则不允许它读取文件。
    *   如果真值作为第二个参数传递，那么执行权限仅适用于所有者，否则适用于所有人

    **第二次过载:**

*   如果真值作为参数传递，则允许它读取抽象路径名，否则不允许它读取文件。

**返回值:**这个函数返回布尔值，不管操作成功与否。

**异常:**如果不允许函数对文件进行写访问，该方法抛出**安全异常**。

下面的程序将说明 setReadable()函数的用法

**示例 1:** 我们将尝试更改 f:目录中现有文件的所有者的 setReadable 权限。

```
// Java program to demonstrate the
// use of setReadable() function

import java.io.*;

public class solution {
    public static void main(String args[])
    {

        // try-catch block to handle exceptions
        try {

            // Create a file object
            File f = new File("f:\\program.txt");

            // Check if the Readable permission
            // can be set to new value
            if (f.setReadable(true)) {

                // Display that the Readable permission
                // is be set to new value
                System.out.println("Readable permission"
                                   + " is set");
            }
            else {

                // Display that the Readable permission
                // cannot be set to new value
                System.out.println("Readable permission"
                                   + " cannot be set");
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
Readable permission is set

```

**示例 2:** 我们将尝试更改 f:目录中每个现有文件的 setReadable 权限。

```
// Java program to demonstrate the
// use of setReadable() function

import java.io.*;

public class solution {
    public static void main(String args[])
    {

        // try-catch block to handle exceptions
        try {

            // Create a file object
            File f = new File("f:\\program.txt");

            // Check if the Readable permission
            // can be set to new value
            if (f.setReadable(true, false)) {

                // Display that the Readable permission
                // is be set to new value
                System.out.println("Readable permission"
                                   + " is set");
            }
            else {

                // Display that the Readable permission
                // cannot be set to new value
                System.out.println("Readable permission"
                                   + " cannot be set");
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
Readable permission is set

```

**程序可能无法在在线 IDE 中运行。请使用离线 IDE 并设置文件的父文件**