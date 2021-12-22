# 用示例在 Java 中文件 setLastModified()方法

> 原文:[https://www . geesforgeks . org/file-setlastpmodified-method-in-Java-with-examples/](https://www.geeksforgeeks.org/file-setlastmodified-method-in-java-with-examples/)

**setlastmodied()**方法是[文件](https://www.geeksforgeeks.org/File-class-in-java/)类的一部分。该函数设置文件或目录的最后修改时间。该函数以毫秒为单位设置文件的最后修改值。
**功能签名:**

```java
public boolean setLastModified(long time)
```

**函数语法:**

```java
file.setLastModified(time)
```

**参数:**该函数接受一个长值作为参数，表示新的最后修改时间。
**返回值:**该函数返回一个布尔值，表示是否设置了新的上次修改时间。
**异常；**该方法抛出以下异常:

*   **安全异常**如果不允许函数对文件进行写访问
*   **IllegalArgumentException** 如果参数为负

下面的程序将说明 setLastModified()函数的使用:
**示例 1:** 我们将尝试更改 f:目录中现有文件的最后修改时间。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate the
// use of setLastModified() function

import java.io.*;

public class solution {
    public static void main(String args[])
    {

        // try-catch block to handle exceptions
        try {

            // Create a file object
            File f = new File("f:\\program.txt");

            // The new last modified time
            long time = 100000000;

            // Check if the last modified time
            // can be set to new value
            if (f.setLastModified(time)) {

                // Display that the last modified time
                // is set as the function returned true
                System.out.println("Last modified time is set");
            }
            else {

                // Display that the last modified time
                // cannot be set as the function returned false
                System.out.println("Last modified time cannot be set");
            }
        }
        catch (Exception e) {
            System.err.println(e.getMessage());
        }
    }
}
```

**输出:**

```java
Last modified time is set
```

**示例 2:** 我们将尝试更改 f:目录中不存在的文件的上次修改时间。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate the
// use of setLastModified() function

import java.io.*;

public class solution {
    public static void main(String args[])
    {

        // try-catch block to handle exceptions
        try {

            // Create a file object
            File f = new File("f:\\program1.txt");

            // The new last modified time
            long time = 100000000;

            // Check if the last modified time
            // can be set to new value
            if (f.setLastModified(time)) {

                // Display that the last modified time
                // is set as the function returned true
                System.out.println("Last modified "
                                   + "time is set");
            }
            else {

                // Display that the last modified time
                // cannot be set as
                // the function returned false
                System.out.println("Last modified time"
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

```java
Last modified time cannot be set
```

**程序可能无法在在线 IDE 中运行。请使用离线 IDE，设置文件**的父文件